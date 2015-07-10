# CLRecipe - Social Media Recipes for TinCan API (xAPI)

## Content Curation Examples

Json files for each example are in the contentcuration folder.

* Create Collection

```json
{
    "actor": {
        "account": {
            "homePage": "https://www.pinterest.com",
            "name": "aneeshabakharia"
        },
        "mbox": "mailto:aneesha.bakharia@gmail.com",
        "name": "Aneesha Bakharia",
        "objectType": "Agent"
    },
    "context": {
        "contextActivities": {
            "grouping": [],
            "other": [],
            "parent": []
        },
        "platform": "Pinterest",
        "registration": "8cb81677-2efe-4bc6-be80-72ff86c68f9e"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "Social Network Analysis"
            },
            "type": "http://activitystrea.ms/head/activity-schema.html#collection"
        },
        "id": "https://www.pinterest.com/aneeshabakharia/social-network-analysis/",
        "objectType": "Activity"
    },
    "timestamp": "2015-07-10T11:51:04.658690",
    "verb": {
        "display": {
            "en-US": "created"
        },
        "id": "http://activitystrea.ms/schema/1.0/create"
    },
    "version": "1.0.1"
}
```

* Tagging Collection

```json
{
    "actor": {
        "account": {
            "homePage": "https://www.pinterest.com",
            "name": "aneeshabakharia"
        },
        "mbox": "mailto:aneesha.bakharia@gmail.com",
        "name": "Aneesha Bakharia",
        "objectType": "Agent"
    },
    "context": {
        "contextActivities": {
            "grouping": [],
            "other": [
                {
                    "definition": {
                        "name": {
                            "en-US": "sna"
                        },
                        "type": "http://id.tincanapi.com/activitytype/tag"
                    },
                    "id": "http://id.tincanapi.com/activity/tags/tincan",
                    "objectType": "Activity"
                }
            ],
            "parent": []
        },
        "platform": "Pinterest",
        "registration": "b23ddaab-1f5b-4f5d-81c3-b67a7f0b5ef4"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "Social Network Analysis"
            },
            "type": "http://activitystrea.ms/head/activity-schema.html#collection"
        },
        "id": "https://www.pinterest.com/aneeshabakharia/social-network-analysis/",
        "objectType": "Activity"
    },
    "timestamp": "2015-07-10T11:51:04.658690",
    "verb": {
        "display": {
            "en-US": "created"
        },
        "id": "http://activitystrea.ms/schema/1.0/create"
    },
    "version": "1.0.1"
}
```

* Adding Media to Collection

```json
{
    "actor": {
        "account": {
            "homePage": "https://www.pinterest.com",
            "name": "aneeshabakharia"
        },
        "mbox": "mailto:aneesha.bakharia@gmail.com",
        "name": "Aneesha Bakharia",
        "objectType": "Agent"
    },
    "context": {
        "contextActivities": {
            "grouping": [],
            "other": [],
            "parent": []
        },
        "platform": "Pinterest",
        "registration": "c75fb8c2-9091-4f70-958b-fe0dff8d1f97"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "2-mode Network"
            },
            "type": "http://adlnet.gov/expapi/activities/link"
        },
        "id": "https://www.pinterest.com/aneeshabakharia/social-network-analysis/",
        "objectType": "Activity"
    },
    "timestamp": "2015-07-10T11:51:04.658690",
    "verb": {
        "display": {
            "en-US": "added"
        },
        "id": "http://activitystrea.ms/schema/1.0/add"
    },
    "version": "1.0.1"
}
```
