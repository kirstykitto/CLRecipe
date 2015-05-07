# CLRecipe - Social Media Recipes for TinCan API (xAPI)

## Content Authoring Examples
* Blog Post
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.randomsyntax.com/",
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
    "objectType": "Article",
    "definition": {
      "name": {
        "en-US": "Blog post text"
      },
      "type": "http://activitystrea.ms/schema/1.0/article"
    }
  },
  "context": {
    "platform": "WordPress",
    "contextActivities": {}
  }
}
```

* Blog Post with Tags
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.randomsyntax.com/",
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
    "objectType": "Article",
    "definition": {
      "name": {
        "en-US": "Blog post text"
      },
      "type": "http://activitystrea.ms/schema/1.0/article"
    }
  },
  "context": {
    "instructor": {
      "name": "",
      "mbox": ""
    },
    "platform": "WordPress",
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
        }
      ]
    }
  }
}
```

* Discussion Thread Associated with Blog Post (could be linear or a tree)
