# Project Title

**Stakeholders**: Fred Hampton (fred_hampton@aol.net), Naomi Klein (naomi_klein@aol.net)

**Maintainers**: Alan Turing (alan_turing@aol.net)

**Description**: This is a project description describing our project.

## Conventions

- In the `docs/data_sources.md` file, we would like all data sources to be listed with a source and description. If possible, a data dictionaries would be appreciated as well!
- Work in branches, not the main branch. Make pull requests and wait for a code review.
- Code reviews shouldn't take more than 3 days.
- Use a code formatter (we use [black](https://black.readthedocs.io/en/stable/index.html) and it is configured to automatically run on pull request or push)
- Only one maintainer per jupyter notebook.
- Data held in shared drive

## Project Flow

1. Create data folder on shared drive and put data into a `raw` subfolder, create `processed`, and `final` subfolders as well.
1. Create repository on github for code, update ReadMe with information about the project (stakeholders, data sources, description, goals, maintainers).
1. Download repository onto aws `GISUSER_` machine.
1. Explore data in QGIS or ArcGIS.
1. Exploratory data cleaning steps are written in jupyter notebooks, but when they're finalized, we transfer them to data pipelines.
1. Create a `requirements.txt` file with all libraries needed for project (arcpy, geopandas, tqdm, etc.), maybe enforce conda environments
1. Let's not commit any code to the master branch ever. Let's make sure we are working branches and making PRs, and getting code reviewed by a peer before pushing into master.

   - `git checkout -b <branchname>`
   - `git add <fileame>`
   - `git commit -m 'message'`
   - `git push`

1. When finish a feature or a work sprint, make a pull request into the master branch and request a code review. Someone other than you reviews the code (if Rohit pushes, Mushtaaq reviews, if Mushtaaq pushes, Rohit reviews).
1. If the code looks good, push into `main` branch, otherwise offer feedback, and do another code review cycle
1. Write code for storing data in s3 buckets.

## Contributing Guidelines

This is the American Forests template of how we structure our code.
In the `scripts/` folder, we have our data cleaning code scripts; this is considered production code and we aim for all code in this folder to be stable and runnable by everyone.
In the `notebooks/` folder, we have our jupyter notebooks.
We recognize that is difficult for multiple people to edit the same Jupyter Notebook because of the challenges around merge conflicts.
Instead, we advise that instead of multiple people collaborating on a single notebook, folks use the notebooks to explore data, generate graphs, etc., however if they plan on collaborating with anyone else on the project, they move any stable code to regular `*.py` files.

If you are working in R cleaning scripts, or R markdown files, you can leave the code in those formats as they don't face the same merge conflicts that jupyter notebooks face. Those files should be kept in the `scripts/` folders.

For internal only projects, we want folks to follow the convention of working in branches, not working in the main branch.
When you have finished a feature, piece of analysis, or cleaning steps, please make a pull request from your branch to the main branch.
Everyone's code should be reviewed by another team member before it is pulled into the main branch.
We would like to aim for no code review remaining outstanding for more than 3 days to keep projects moving.

Any python3 packages that you are using, should be listed in the `environment.yml` file.

Your data should be held in a _separate_ folder on one of our shared drives.
The folder should have three sub-folders: `raw`, `processed`, `final`.
Any inactive projects should be pushed to s3 to keep space clear on the Shared drives.

## Code Review Guidelines

Code reviews should be kind, constructive, and specific.
We also want to cultivate a culture of peer code reviews, everyone's code is eligible to reviewed by anyone else on their team!
Our hope is that these code reviews lead to best practices, identifying needs for internal tools, and writing maintainable code.
