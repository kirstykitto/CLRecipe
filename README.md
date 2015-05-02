# CLRecipe - Social Media Recipes for TinCan API (xAPI)

The [Connected Learning Analytics Toolkit](https://github.com/kirstykitto) imports social media associated with a learning activity into an LRS and performs advanced analytics. The recipes to model social media interaction as xAPI statements are shared for community contribution and feedback. Recipes for Microblogging, Content Authoring and Content Curation will be provided. 

## Modeling Social Media Interaction as an xAPI statement

The CLRecipe project:
*  maps terminology from various social media platforms to a common set of objects and verb
*  provides xAPI recipes that include the relationship between social media posts (i.e. reply, share and like) so that both content analysis and social network analysis can be performed.

Though social media platforms use different terminology, a common model of interaction exists (see figure below). The model involves:
* a user making a post
* a user optionally including a tag, hashtag or mentioning other users
* a user sharing a post on their timeline (i.e. for their followers to view)
* a user replying (and optionally including a comment) to a post

### Objects

Objects are items that are created on social media platforms. Blog posts, tweets, homepage posts and curated media are all example objects. The CLRecipe makes a distinction between short Microblogging posts (i.e. using the Note object) and larger text articles (i.e. using the Article object).

| Object  | Description | Source |
| ------------- | ------------- | ------------- |
| Note  | Represents a short-form text message. This object is intended primarily for use in "micro-blogging" scenarios and in systems where users are invited to publish short, often plain-text messages.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#note) |
| Article | Represents objects such as news articles, knowledge base entries, or other similar construct. Such objects generally consist of paragraphs of text, in some cases incorporating embedded media such as photos and inline hyperlinks to other resources.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#article) |
| Comment | Represents a textual response to another object. Objects of this type MAY contain an additional inReplyTo property whose value is an Array of one or more other Activity Stream Objects for which the object is to be considered a response. | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#comment) |
| Collection | Represents a generic collection of objects of any type.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#collection) |

Object use by platform:

|   | Note | Article | Comment |
| ------------- | ------------- | ------------- | ------------- |
| Facebook Group | Yes | Yes | Yes |
| Google+ Group | Yes | Yes | Yes |
| Twitter | Yes |  |  |
| Blog | | Yes  | Yes |

### Verbs

Verbs are actions that are performed on an object.

| Verb  | Description | Source |
| ------------- | ------------- | ------------- |
| Create  | Indicates that the actor has created the object.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#verbs) |
| Like  |  Indicates that the actor marked the object as an item of special interest. The "like" verb is considered to be an alias of "favorite". The two verb are semantically identical. | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#verbs) |
| Share  | Indicates that the actor has called out the object to readers. In most cases, the actor did not create the object being shared, but is instead drawing attention to it.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#verbs) |
| Tag  | Activity generally used in the "other" or "grouping" Context Activities lists to mark a statement as being related to a particular subject area. Implemented as a one word identifier used for search filtering or tag cloud generation. Includes hashtagging for tweets. | [TINCAN API](http://id.tincanapi.com/activitytype/tag) |
| Rate  | Value is an object that is similar to the Result's "score" property in that it should include a 'raw' value as well as 'min' and 'max' range indicators. | [TINCAN API](http://id.tincanapi.com/extension/quality-rating) |

Verb use by platform:

|   | Share | Tag | Hashtag | Mentions |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Facebook Group | Yes | Yes | Yes | Yes |
| Google+ Group | Yes | Yes | Yes | Yes |
| Twitter | Yes |  | Yes | Yes |
| Blog | | Yes  |  |  |


## Example TinCan Statements

### Microblogging
* Create a Tweet

```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.twitter.com/aneesha",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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
      "homepage": "http://www.twitter.com/aneesha",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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
      "homepage": "http://www.twitter.com/aneesha",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/share",
    "display": {
      "en-US": "Share"
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

* Retweet with Comment

* Favorite (or Like) a Tweet
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.twitter.com/aneesha",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/like",
    "display": {
      "en-US": "Like"
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

### Content Authoring
* Blog Post
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.randomsyntax.com/about",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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
      "homepage": "http://www.randomsyntax.com/about",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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

### Collaborative Content Authoring (Todo)
* Adding Content
* Editing Content
* Deleting Content
* Linking (Associating Content)
* Tagging Content
* Tagging Collections

### Content Curation (Todo)
* Create Collection
* Adding Media to Collection
* Tagging Media in a Collection
* Tagging Collection
* Sharing Collection
* Sharing Item in Collection

## Associating Social Media Statement with a Course, Team (or Group) and Instructor
* Associating with an Instructor
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.randomsyntax.com/about",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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
      "name": "Aneesha Bakharia",
      "mbox": "test@mail.com"
    },
    "platform": "WordPress",
    "contextActivities": {}
  }
}
```

* Associate with a Course
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.randomsyntax.com/about",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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
    "contextActivities": {
      "group": {
        "id": "ABC600",
        "type": "http://adlnet.gov/expapi/activities/course"
      }
    }
  }
}
```

* Associate with a Team or Group
```json
{
  "actor": {
    "objecttype": "Agent",
    "account": {
      "homepage": "http://www.randomsyntax.com/about",
      "name": "aneesha"
    }
  },
  "verb": {
    "id": "http://activitystrea.ms/schema/1.0/create",
    "display": {
      "en-US": "Create"
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
    "team": {
      "name": "Tut Group 1",
      "objectType": "Group"
    },
    "contextActivities": {}
  }
}
```

## Useful TinCan API Recipes
* [SCORM to Tincan API Cookbook](http://tincanapi.com/scorm-to-tin-can-api-cookbook/)
* [xAPI community of practice for user generated course content (UGCC)](https://github.com/ht2/UGCC-CoP)
* [xAPI Community of Practice for Mozilla Open Badges](https://github.com/ht2/UGCC-CoP)
* [Verbs and Activity Types used in Curatr](http://www.curatr3.com/admin-guide/#document-12)

## References
* [xAPI Specification](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI.md)
