# dbt Exercise Instructions #
- Let's add dbt tests to our data warehouse and set it up to be refreshed on a schedule.

### dbt Testing ###
- There are 4 built in dbt data tests. We are going to add each test to our data warehouse so that we can see how they all work. There are many more tests you can add to your dbt project through packages and you can even write your own tests. We are just going to focus on the 4 built in data tests in this class.

- Login to GitHub
- Go to your repository you created when you set up dbt cloud
- Click Branches
    - New Branch
    - Call the new branch 'Core6'
    - Click Create New Branch

- Login to dbt Cloud
- Click Studio
- Click 'Change Branch'
    - Select the new branch we just created called 'Core6'


- We will add all of our tests in the `_schema_oliver.yml` file

#### unique ####
- The unique test ensures that each record has a unique value for a given field.

- Add a unique test to a model

```

```

- Run `dbt build -s dim_policy` to ensure that the test passes.

#### not_null ####
- The not_null test ensures no records have a null value for a given field.

- Add the not_null test to a model

```
```

#### accepted_values ####
- The accepted values test ensures that only certain values can be present in a given field

- Add the accepted values to a model

```

```

#### relationships ####
- The relationships test ensures that every key that exist on a table (usually a fact) also exists on the foreign table (usually a dim)

- Add the relationships test to a model

```

```

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
- Change the Sync frequency to `12 hours` on your oliver connector

#### dbt Cloud ####
- You can use your previous production environment you created in the exercise, so no need to create a new environment.

- Click on the Orchestration Tab
- Click on Jobs
- Click New Job
- Click Deploy Job
- Name the job `Oliver DW Refresh`
- Under commands type a command that builds everything in your oliver DW
- Enable the Run on Schedule option
- Change timing to Specific Hours
- Set Run at (UTC) = 6 (This is the equivalent of midnight in MDT)
- Click Save
- Click Run Now
- Click the running job to view the results to ensure it runs successfully

- __Submit a screenshot of the completion of your job showing each model/test that ran successfully__