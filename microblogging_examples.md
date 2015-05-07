# CLRecipe - Social Media Recipes for TinCan API (xAPI)

## Microblogging Examples

* Create a Tweet

```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.twitter.com/",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "created"
    }
  },
  "object": {
    "id": "https://twitter.com/aneesha/status/593190361255677952",
    "objectType": "Note",
    "definition": {
      "name": {
        "en-US": "i'm having the worst luck with ordering electronic components online - orders arrive but are always missing crucial things"
      },
      "type": "http://activitystrea.ms/schema/1.0/note"
    }
  },
  "context": {
    "platform": "Twitter",
    "contextActivities": {}
  }
}
```

* Include Hashtag/s and @mention/s in a Microblog Post

```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.twitter.com/",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "created"
    }
  },
  "object": {
    "id": "https://twitter.com/aneesha/status/593190361255677952",
    "objectType": "Note",
    "definition": {
      "name": {
        "en-US": "i'm having the worst luck with ordering electronic components online - orders arrive but are always missing crucial things"
      },
      "type": "http://activitystrea.ms/schema/1.0/note"
    }
  },
  "context": {
    "platform": "Twitter",
    "contextActivities": {
      "other": [
        {
          "id": "http://id.tincanapi.com/activity/tags/tincan",
          "objecttype": "Activity",
          "definition": {
            "type": "http://id.tincanapi.com/activitytype/tag",
            "name": {
              "en-US": "tag2"
            }
          }
        },
        {
          "id": "http://id.tincanapi.com/activity/tags/tincan",
          "objecttype": "Activity",
          "definition": {
            "type": "http://id.tincanapi.com/activitytype/tag",
            "name": {
              "en-US": "tag2"
            }
          }
        },
        {
          "id": "http://id.tincanapi.com/activity/tags/tincan",
          "objecttype": "Activity",
          "definition": {
            "type": "http://id.tincanapi.com/activitytype/tag",
            "name": {
              "en-US": "@aneesha"
            }
          }
        }
      ]
    }
  }
}
```

* Retweet

```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.twitter.com/",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/share",
    "display": {
      "en-US": "shared"
    }
  },
  "object": {
    "id": "https://twitter.com/aneesha/status/593190361255677952",
    "objectType": "Note",
    "definition": {
      "name": {
        "en-US": "i'm having the worst luck with ordering electronic components online - orders arrive but are always missing crucial things"
      },
      "type": "http://activitystrea.ms/schema/1.0/note"
    }
  },
  "context": {
    "platform": "Twitter",
    "contextActivities": {
      "parent": {
        "id": "https://twitter.com/aneesha/status/593190361255677952",
        "objecttype": "Note"
      }
    }
  }
}
```

* Favorite (or Like) a Tweet
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.twitter.com/",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/like",
    "display": {
      "en-US": "liked"
    }
  },
  "object": {
    "id": "https://twitter.com/aneesha/status/593190361255677952",
    "objectType": "Note",
    "definition": {
      "name": {
        "en-US": ""
      },
      "type": "http://activitystrea.ms/schema/1.0/note"
    }
  },
  "context": {
    "platform": "Twitter",
    "contextActivities": {
      "parent": {
        "id": "https://twitter.com/aneesha/status/593190361255677952",
        "objecttype": "Note"
      }
    }
  }
}
```
