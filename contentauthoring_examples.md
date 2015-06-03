# CLRecipe - Social Media Recipes for TinCan API (xAPI)

## Content Authoring Examples

Json files for each example are in the contentauthoring folder.

* Blog Post
```json
{
    "actor": {
        "account": {
            "homePage": "http://www.syntaxspectrum.com/",
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
        "platform": "WordPress",
        "registration": "32c00f3f-198d-4274-8d6f-5ea92fa9c228"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "5 Ways Coursera has Advanced the MOOC"
            },
            "type": "http://activitystrea.ms/schema/1.0/article"
        },
        "id": "http://syntaxspectrum.com/2013/08/5-ways-coursera-has-advanced-the-mooc/",
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

* Blog Post with Tags
```json
{
    "actor": {
        "account": {
            "homePage": "http://www.syntaxspectrum.com/",
            "name": "aneesha"
        },
        "objectType": "Agent"
    },
    "context": {
        "contextActivities": {
            "grouping": [],
            "other": [
                {
                    "definition": {
                        "name": {
                            "en-US": "coursera"
                        },
                        "type": "http://id.tincanapi.com/activitytype/tag"
                    },
                    "id": "http://id.tincanapi.com/activity/tags/tincan",
                    "objectType": "Activity"
                }
            ],
            "parent": []
        },
        "platform": "WordPress",
        "registration": "a09c3765-77ff-470b-8c77-9c694019a8b8"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "5 Ways Coursera has Advanced the MOOC"
            },
            "type": "http://activitystrea.ms/schema/1.0/article"
        },
        "id": "http://syntaxspectrum.com/2013/08/5-ways-coursera-has-advanced-the-mooc/",
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

* Rate a Blog
```json
{
    "actor": {
        "account": {
            "homePage": "http://www.syntaxspectrum.com/",
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
        "platform": "WordPress",
        "registration": "b8f67074-26ab-44d4-beb7-67e7f45f329a"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "5 Ways Coursera has Advanced the MOOC"
            },
            "type": "http://activitystrea.ms/schema/1.0/article"
        },
        "id": "http://syntaxspectrum.com/2013/08/5-ways-coursera-has-advanced-the-mooc/",
        "objectType": "Activity"
    },
    "result": {
        "score": {
            "raw": 5.0
        }
    },
    "verb": {
        "display": {
            "en-US": "rated"
        },
        "id": "http://id.tincanapi.com/verb/rated"
    }
}
```

* Discussion Thread Associated with Blog Post (could be linear or a tree)
```json
{
    "actor": {
        "account": {
            "homePage": "http://www.syntaxspectrum.com/",
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
        "platform": "WordPress",
        "registration": "dc19e09e-844a-4b30-8277-9b7bec47ea6b"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "5 Ways Coursera has Advanced the MOOC"
            },
            "type": "http://activitystrea.ms/schema/1.0/article"
        },
        "id": "http://syntaxspectrum.com/2013/08/5-ways-coursera-has-advanced-the-mooc/#comment-1086",
        "objectType": "Activity"
    },
    "verb": {
        "display": {
            "en-US": "commented"
        },
        "id": "http://adlnet.gov/expapi/verbs/commented"
    }
}
```
