
# Rocket.Chat GSoC Contributions Leaderboard

![Rocket.Chat GSoC Contributions Leaderboard screenshot](https://github.com/Sing-Li/bbug/blob/master/images/leaderboard.png)

A contributions leaderboard for your GSoC organization. Students can track their position on leaderboard based on the PRs, commits, and issues they've completed across the repositories of your organization on Github.

## Benefits
- Encourage students to improve their position - by increasing contribution to your organization
- Easy to setup and administer
- Realtime organization-wide visibility to top student candidates

## Main Features
- Track commits/PRs/issues for GSoC student candidates in real time
- At a glance view of participating top students
- Easy administration to add students (even before they have made their very first contribution)

## Quick Start

Make sure you have the following linux dependencies installed:

- Python3
- django
- dj-database-url
- gunicorn
- psycopg
- requests
- PyGithub
- python-decouple
- django-bootstrap4

Then, clone the repository to your local machine:

```bash
git clone https://github.com/shubhsherl/GSoC-Contribution-Leaderboard.git
```

Install the requirements:

```bash
pip install -r requirements.txt
```

Add your Github Auth Token and Organization name in `RC_leaderboard/setting.py`

Create the database:

```bash
python manage.py migrate
```

Finally, run the development server:

```bash
python manage.py runserver
```


First, create a superuser:

```bash
python manage.py createsuperuser
```

#### Setting up adminsistration

- Run the project, and Refresh to get the Repo of your Organization.
- Visit `/admin` and login using the created superuser.
- Add Repositories to include in Leaderboard.
- Refresh again to get the contributors of your Organization.
- Add/Remove user to GSoC list using action in Core>Users.

The project will be available at **127.0.0.1:8000** by default.

##### Admin levels:
- **Exclude Repo:** Decide which Repo to count for LeaderBoard
- **Moderator:** The above plus the ability to kick and ban users

## Description of files in Repository

Non-Python files:

filename                           |  description
----------------------------------|------------------------------------------------------------------------------------
README.md                         |  Text file (markdown format) description of the project.
requirement.txt                   |  list all packages that needs to be installed for the project.
\*.html                           |  html file for rendering web-page

Python scripts files:

filename                           |  description
----------------------------------|------------------------------------------------------------------------------------
glist.py                          |  Fetch and refresh data of GSoC candidate from the local sqlite3 database.
model.py                          |  Contains the User and Repository Model for database.
admin.py                          |  Contains the Admin Model for Administrator dashboard.
view.py                           |  Fetch and refresh data from the Github database to a local sqlite3 database.
setting.py                        |  Django file for settings of Project.


## Contributing

We welcome all contributions for any GSoC orgs, students, or community members. Feel free to contribute bug-fixes at any time. If you plan to contribute new features, utility functions or extensions, please first create an issue and discuss the feature with us. Please help us to improve our documentation, including this page!

### Some suggested  features to add
- Show details of contribution when clicked on counts
- Add `Lines Added/Deleted` stats.
- Show personalized chart of commits/issues/PRs

