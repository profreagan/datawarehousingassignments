# Exercise: Introduction to GitHub

# Learning Objectives

By completing this assignment, you will:

-   Create and structure a GitHub repository
-   Write a simple Python file in the browser
-   Work in branches
-   Open and describe a Pull Request
-   Add a collaborator
-   Approve and merge a Pull Request
-   Learn the GitHub flow

# Part 1 --- Create Your Repository

1.  Go to GitHub.com

2.  Click **New Repository**

3.  Repository name:

    `introtogithub`

4.  Set to **Public**

5.  Check:

    -   ✅ Add a README file\

6.  Click **Create repository**

# Part 2 --- Create Your First Branch 

You may not edit `main`.

1.  Go to your repository.

2.  Click the branch dropdown (currently says `main`).

3.  Create a new branch named:

    `setup-readme`

You should now be working in `setup-readme`.

# Part 3 --- Edit README in Your Branch

While on `setup-readme`, click the pencil icon on `README.md`.

Replace its contents with:

``` md
# Introduction to GitHub

## About Me
- Name:
- Major:
- Career interest:

## Why Version Control Matters
Write 3–5 sentences explaining why version control is important in data projects.
```

Scroll down.

Commit settings: - Ensure it says: **Commit directly to the setup-readme
branch** - Commit message:

`Update README with introduction`

## Open a Pull Request

1.  Go to **Pull Requests**

2.  Click **New Pull Request**

3.  Compare:

    -   Base: `main`
    -   Compare: `setup-readme`

4.  Comment

    Make a comment regarding what/why you did what you did.

Create the Pull Request.

**Do NOT merge yet.**


# Part 4 --- Add a Simple Python File 

Now create a new branch.

1.  Go back to the repository main page.

2.  Create a new branch named:

    `add-python-file`


## Create a Python File

1.  Click **Add file → Create new file**

2.  Name it:

    `hello.py`

Add this simple code:

``` python
name = "YourName"
print("Hello, " + name)
```

Replace `YourName` with your actual name.

Commit message:

`Add simple hello script`

Make sure it commits to `add-python-file`, **not main**.


## Open a Pull Request

1.  Go to **Pull Requests**
2.  Click **New Pull Request**
3.  Compare:
    -   Base: `main`
    -   Compare: `add-python-file`

Title:

`Add hello.py script`

In the description: - What does this code do? 

Create the Pull Request.

**Do NOT merge yet.**

# Part 5 --- Add a Collaborator 

You will be assigned a partner.

1.  Go to **Settings**
2.  Click **Collaborators**
3.  Click **Add people**
4.  Add your partner's GitHub username
5.  They must accept the invitation

You must also accept their invitation.


# Part 6 --- Approve Each Other's Pull Requests

Go to your partner's repository.

For at least one of their Pull Requests:

1.  Click **Files changed**
2.  Click **Review changes**
3.  Leave one comment
4.  Click **Approve**

Your partner must approve at least one of yours.

# Part 7 --- Merge Only After Approval 

Once your PR shows **Approved**:

1.  Click **Merge Pull Request**
2.  Confirm merge
3.  Delete the branch

You should now have:

-   No direct commits to `main`
-   Two merged Pull Requests
-   Deleted branches


# Submission 

Submit:

1.  Link to your repository
2.  Link to one of your Pull Requests

# Why This Matters for dbt

In dbt, you will:

-   Never push directly to production (`main`)
-   Build features in branches
-   Open Pull Requests
