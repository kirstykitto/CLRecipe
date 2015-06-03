# CLRecipe - Social Media Recipes for TinCan API (xAPI)


## Associating Social Media Statement with a Course, Team (or Group) and Instructor

Json files for each example are in the courseteaminstructor folder.

* Associating with an Instructor
```json
{
    "actor": {
        "account": {
            "homePage": "http://www.twitter.com",
            "name": "aneesha"
        },
        "objectType": "Agent"
    },
    "context": {
        "contextActivities": {
            "grouping": [],
            "other": [],
            "parent": []
        },
        "instructor": {
            "mbox": "mailto:email@test.com",
            "name": "Kirty Kitto",
            "objectType": "Agent"
        },
        "platform": "Twitter",
        "registration": "9fedac48-8e48-428b-b7e8-60d8088a476b"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "Just discovered Sirius - a graphical modeling workbench http://www.eclipse.org/sirius/overview.html"
            },
            "type": "http://activitystrea.ms/schema/1.0/note"
        },
        "id": "https://twitter.com/aneesha/status/605894039666171904",
        "objectType": "Activity"
    },
    "verb": {
        "display": {
            "en-US": "created"
        },
        "id": "http://activitystrea.ms/schema/1.0/create"
    }
}
```

* Associate with a Course
```json
{
    "actor": {
        "account": {
            "homePage": "http://www.twitter.com",
            "name": "aneesha"
        },
        "objectType": "Agent"
    },
    "context": {
        "contextActivities": {
            "grouping": [
                {
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/course"
                    },
                    "id": "ABC101",
                    "objectType": "Activity"
                }
            ],
            "other": [],
            "parent": []
        },
        "platform": "Twitter",
        "registration": "a219cc67-acd3-4e3b-82c9-3fda9146b21c"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "Just discovered Sirius - a graphical modeling workbench http://www.eclipse.org/sirius/overview.html"
            },
            "type": "http://activitystrea.ms/schema/1.0/note"
        },
        "id": "https://twitter.com/aneesha/status/605894039666171904",
        "objectType": "Activity"
    },
    "verb": {
        "display": {
            "en-US": "created"
        },
        "id": "http://activitystrea.ms/schema/1.0/create"
    }
}
```
