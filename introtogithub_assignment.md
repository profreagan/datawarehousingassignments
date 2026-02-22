# Assignment: Introduction to GitHub (Browser Only)

## Important Rules

-   Use GitHub in your **browser only**.
-   Do **NOT** use GitHub Desktop or the terminal.
-   You may **NOT** commit directly to the `main` branch.
-   All changes must go through a **Pull Request**.

------------------------------------------------------------------------

# Learning Objectives

By completing this assignment, you will:

-   Create and structure a GitHub repository\
-   Write a simple Python file in the browser\
-   Work in branches (not `main`)\
-   Open and describe a Pull Request\
-   Add a collaborator\
-   Approve and merge a Pull Request

This mirrors professional analytics workflows.

------------------------------------------------------------------------

# Part 1 --- Create Your Repository (10 points)

1.  Go to GitHub.com\

2.  Click **New Repository**\

3.  Repository name:

    `introtogithub`

4.  Set to **Public**\

5.  Check:

    -   ✅ Add a README file\

6.  Click **Create repository**

------------------------------------------------------------------------

# Part 2 --- Create Your First Branch (10 points)

You may not edit `main`.

1.  Go to your repository.\

2.  Click the branch dropdown (currently says `main`).\

3.  Create a new branch named:

    `setup-readme`

You should now be working in `setup-readme`.

------------------------------------------------------------------------

# Part 3 --- Edit README in Your Branch (15 points)

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

------------------------------------------------------------------------

## Open a Pull Request

1.  Go to **Pull Requests**\

2.  Click **New Pull Request**\

3.  Compare:

    -   Base: `main`
    -   Compare: `setup-readme`

4.  Title:

    `Add personal introduction to README`

In the description, answer: - What did you add? - Why is it better than
the original README?

Create the Pull Request.

**Do NOT merge yet.**

------------------------------------------------------------------------

# Part 4 --- Add a Simple Python File (20 points)

Now create a new branch.

1.  Go back to the repository main page.\

2.  Create a new branch named:

    `add-python-file`

------------------------------------------------------------------------

## Create a Python File

1.  Click **Add file → Create new file**\

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

------------------------------------------------------------------------

## Open a Pull Request

1.  Go to **Pull Requests**\
2.  Click **New Pull Request**\
3.  Compare:
    -   Base: `main`
    -   Compare: `add-python-file`

Title:

`Add hello.py script`

In the description: - What does this code do? - Why is it useful to test
code in small steps?

Create the Pull Request.

**Do NOT merge yet.**

------------------------------------------------------------------------

# Part 5 --- Add a Collaborator (10 points)

You will be assigned a partner.

1.  Go to **Settings**\
2.  Click **Collaborators**\
3.  Click **Add people**\
4.  Add your partner's GitHub username\
5.  They must accept the invitation

You must also accept their invitation.

------------------------------------------------------------------------

# Part 6 --- Approve Each Other's Pull Requests (15 points)

Go to your partner's repository.

For at least one of their Pull Requests:

1.  Click **Files changed**\
2.  Click **Review changes**\
3.  Leave one comment\
4.  Click **Approve**

Your partner must approve at least one of yours.

------------------------------------------------------------------------

# Part 7 --- Merge Only After Approval (10 points)

Once your PR shows **Approved**:

1.  Click **Merge Pull Request**\
2.  Confirm merge\
3.  Delete the branch

You should now have:

-   No direct commits to `main`\
-   Two merged Pull Requests\
-   Deleted branches

------------------------------------------------------------------------

# Submission (10 points)

Submit:

1.  Link to your repository\
2.  Link to one of your Pull Requests\
3.  Screenshot showing:
    -   An approved PR\
    -   Your collaborator listed in Settings

------------------------------------------------------------------------

# Grading Rubric (100 points)

  Criteria                            Points
  ----------------------------------- --------
  Repository created correctly        10
  No commits made directly to main    15
  README branch + PR completed        15
  Python file branch + PR completed   20
  Collaborator added                  10
  Approval given to partner           15
  Professional commit messages        10
  Branches deleted after merge        5

------------------------------------------------------------------------

# Why This Matters for dbt

In dbt, you will:

-   Never push directly to production (`main`)\
-   Build features in branches\
-   Open Pull Requests\
-   Require approval before merging

This is exactly how analytics engineering teams operate.
