# dbt Exercise Instructions #
- Let's add dbt tests to our data warehouse and set it up to be refreshed on a schedule.

### dbt Testing ###
- There are 4 built in dbt data tests. We are going to add each test to our data warehouse so that we can see how they all work. There are many more tests you can add to your dbt project through packages and you can even write your own tests. We are just going to focus on the 4 built in data tests in this class.

- Login to GitHub
- Go to your repository you created when you set up dbt cloud
- Click Branches
    - New Branch
    - Call the new branch 'Exercise_dbt_part3'
    - Click Create New Branch

- Login to dbt Cloud
- Click Studio
- Click 'Change Branch'
    - Select the new branch we just created called 'Exericse_dbt_part3'


- We will add all of our tests in the `_schema_insurance.yml` file

#### unique ####
- The unique test ensures that each record has a unique value for a given field.

- Add the unique test to the `policy_key` in the `dim_policy` model:

```
  - name: dim_policy
    description: "Insurance Policy Dimension"
    columns:
      - name: policy_key
        tests:
          - unique
```

- Run `dbt build -s dim_policy` to ensure that the test passes.

#### not_null ####
- The not_null test ensures no records have a null value for a given field.

- Add the not_null test to the `policy_key` in the `fact_claim` model:

```
  - name: fact_claim
    description: "Insurance Claim Fact"
    columns:
      - name: policy_key
        description: "A foreign key to the policy dimension"
        tests:
          - not_null
```

- Run `dbt build -s fact_claim` to ensure that the test passes.

#### accepted_values ####
- The accepted values test ensures that only certain values can be present in a given field

- Add the accepted values to the `issue_type` field in the `stg_customer_service_interactions` model:

```
  - name: stg_customer_service_interactions
    description: |
      Staging model for customer service interactions.
      Each record represents a call between a customer and an agent.
    columns:
      - name: issue_type
        tests:
          - accepted_values:
              values:
                - "New Claim"
                - "Claim Status"
                - "Policy Change"
                - "Coverage Info"
                - "Billing Issue"
                - "Policy Renewal"
```

- Run `dbt build -s stg_customer_service_interactions` to ensure that the test passes.

#### relationships ####
- The relationships test ensures that every key that exist on a table (usually a fact) also exists on the foreign table (usually a dim)

- Add the relationships test to the `customer_key` field on the `fact_interaction` model:

```
  - name: fact_interaction
    description: |
      Customer Service Interaction Fact.
      The grain of this table is customer + agent + date
      Each record represents a call between a customer and an agent on a given date.
    columns:
      - name: customer_key
        tests:
          - relationships:
              to: ref('dim_customer') # the model you want to compare to
              field: customer_key # the field on the model you want to compare to
```

- Run `dbt build -s fact_interaction` to ensure that the test passes.

## Create a Pull Request on GitHub for the changes you have made ##
- Click Save on any files that you have made changes in.
- Click `Commit and Sync`
- Type a commit message explaining the changes you've made. Click `Commit Changes`.
- Click `Create a pull request on GitHub`
    - You will be redirected to GitHub
- Review your changes and click `Create pull request`
- Type a description about the changes you are proposing to the project.
- Click `Create Pull Request`
- merge your branch into the main branch by clicking `Merge pull request`.

### Scheduling ###

#### Fivetran ####
- Login to Fivetran
- Click on 'Connectors'
- Click on your insurance connector
- Click the Setup tab
- Change the Sync frequency to `12 hours`

#### dbt Cloud ####
- Login to dbt Cloud
- Click on the Orchestration Tab
- Click on Environments
- Click Create New Environment
- Name the Environment `Production`
- Under Connection set the Connection to Snowflake
- Change Auth Method to Key pair
- Type in your Snowflake Username
- Copy the Private Key from the Canvas Assignmnet
- Set Schema to `DW_INSURANCE`
- Click Save


- Click on the Orchestration Tab
- Click on Jobs
- Click New Job
- Click Deploy Job
- Name the job `Insurance DW Refresh`
- Under commands type `dbt build -s insurance.*`
- Enable the Run on Schedule option
- Change timing to Specific Hours
- Set Run at (UTC) = 6 (This is the equivalent of midnight in MDT)
- Click Save
- Click Run Now
- Click the running job to view the results to ensure it runs successfully

- __Submit a screenshot of the completion of your job showing each model/test that ran successfully__