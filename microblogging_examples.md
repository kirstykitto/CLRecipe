# CLRecipe - Social Media Recipes for TinCan API (xAPI)

## Microblogging Examples

Json files for each example are in the microblogging folder.

* Create a Tweet

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
        "platform": "Twitter",
        "registration": "3758473f-2320-494a-85a4-50288f9346a8"
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

* Include Hashtag/s and @mention/s in a Microblog Post

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
            "other": [
                {
                    "definition": {
                        "name": {
                            "en-US": "@sbuckshum"
                        },
                        "type": "http://id.tincanapi.com/activitytype/tag"
                    },
                    "id": "http://id.tincanapi.com/activity/tags/tincan",
                    "objectType": "Activity"
                },
                {
                    "definition": {
                        "name": {
                            "en-US": "#clatest"
                        },
                        "type": "http://id.tincanapi.com/activitytype/tag"
                    },
                    "id": "http://id.tincanapi.com/activity/tags/tincan",
                    "objectType": "Activity"
                }
            ],
            "parent": []
        },
        "platform": "Twitter",
        "registration": "b234b0fc-5f53-4b4b-810b-c52bc65dbf8d"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "making social learning (ephemeral social processes) analytics visible @sbuckshum #clatest"
            },
            "type": "http://activitystrea.ms/schema/1.0/note"
        },
        "id": "https://twitter.com/aneesha/status/597971744180174848",
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

* Retweet

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
            "parent": [
                {
                    "objectType": "Activity"
                }
            ]
        },
        "platform": "Twitter",
        "registration": "943fbb47-1c38-42ff-a321-8aff6605d657"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "Congrats to Facebook on their new Paris lab. "
            },
            "type": "http://activitystrea.ms/schema/1.0/note"
        },
        "id": "https://twitter.com/BaiduResearch/status/605777762893185026",
        "objectType": "Activity"
    },
    "verb": {
        "display": {
            "en-US": "shared"
        },
        "id": "http://activitystrea.ms/schema/1.0/share"
    }
}
```

* Retweet with a comment
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
            "parent": [
                {
                    "id": "https://twitter.com/pythontrending/status/605831255490334722",
                    "objectType": "Activity"
                }
            ]
        },
        "platform": "Twitter",
        "registration": "48e8d97e-8264-44c4-95b9-ded43ea4463e"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "looks useful for neural nets on theano"
            },
            "type": "http://activitystrea.ms/schema/1.0/note"
        },
        "id": "https://twitter.com/aneesha/status/605898487125803009",
        "objectType": "Activity"
    },
    "verb": {
        "display": {
            "en-US": "shared"
        },
        "id": "http://activitystrea.ms/schema/1.0/share"
    }
}
```

* Favorite (or Like) a Tweet
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
            "parent": [
                {
                    "objectType": "Activity"
                }
            ]
        },
        "platform": "Twitter",
        "registration": "505130f5-43cc-4f76-a679-ec670805c8f4"
    },
    "object": {
        "definition": {
            "name": {
                "en-US": "9 Designer Tools Everyone Should Know About http://rightrelevance.com/tw/datavizrr/9b88cfbecdf36bcf07bd0e7ba7ca54c0af87a9c4/data%20visualization/data%20visualization"
            },
            "type": "http://activitystrea.ms/schema/1.0/note"
        },
        "id": "https://twitter.com/DataVizRR/status/605892458413580288",
        "objectType": "Activity"
    },
    "verb": {
        "display": {
            "en-US": "liked"
        },
        "id": "http://activitystrea.ms/schema/1.0/like"
    }
}
```
