# CLRecipe - Social Media Recipes for TinCan API

## Objects

Objects are items that are created on social media platforms. Blog posts, tweets, homepage posts and curated media are all example objects.

| Object  | Description | Source |
| ------------- | ------------- | ------------- |
| Note  | Represents a short-form text message. This object is intended primarily for use in "micro-blogging" scenarios and in systems where users are invited to publish short, often plain-text messages.  | [Activity Stream Schema]() |
| Article | Represents objects such as news articles, knowledge base entries, or other similar construct. Such objects generally consist of paragraphs of text, in some cases incorporating embedded media such as photos and inline hyperlinks to other resources.  | [Activity Stream Schema]() |
| Comment | Represents a textual response to another object. Objects of this type MAY contain an additional inReplyTo property whose value is an Array of one or more other Activity Stream Objects for which the object is to be considered a response. | [Activity Stream Schema]() |
| Group | Represents a grouping of objects in which member objects can join or leave.  | [Activity Stream Schema]() |

## Verbs

Verbs are actions that are performed on an object.

| Verb  | Description | Source |
| ------------- | ------------- | ------------- |
| Create  | Indicates that the actor has created the object.  | [Activity Stream Schema]() |
| Favourite  | Indicates that the actor marked the object as an item of special interest.  | [Activity Stream Schema]() |
| Like  |  Indicates that the actor marked the object as an item of special interest. The "like" verb is considered to be an alias of "favorite". The two verb are semantically identical. | [Activity Stream Schema]() |
| Share  | Indicates that the actor has called out the object to readers. In most cases, the actor did not create the object being shared, but is instead drawing attention to it.  | [Activity Stream Schema]() |
| Tag  | Activity generally used in the "other" or "grouping" Context Activities lists to mark a statement as being related to a particular subject area. Implemented as a one word identifier used for search filtering or tag cloud generation. Does not include hashtagging for tweets. | [TINCAN API](http://id.tincanapi.com/activitytype/tag) |

## Mapping Social Media Platforms to Objects and Verbs

### Object Mapping

|   | Note | Article | Comment |
| ------------- | ------------- | ------------- | ------------- |
| Facebook Group | Yes | Yes | Yes |
| Google+ Group | Yes | Yes | Yes |
| Twitter | Yes |  |  |
| Blog | | Yes  | Yes |

### Verb Mappings

|   | Share | Tag | Hashtag | Mentions |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Facebook Group | Yes | Yes | Yes | Yes |
| Google+ Group | Yes | Yes | Yes | Yes |
| Twitter | Yes |  | Yes | Yes |
| Blog | | Yes  |  |  |

## Example TinCan Statements

### Microblogging
* Send a Tweet
* Retweet
* Retweet with Comment
* Include a Hashtag/s
* Include @mention/s
* Favourite a Tweet

### Content Authoring
* Blog Post
* Discussion Thread Associated with Blog Post (could be linear or a tree)

### Collaborative Content Authoring
* Adding Content
* Editing Content
* Deleting Content
* Linking (Associating Content)
* Tagging Content
* Tagging Collections

### Content Curation
* Create Collection
* Adding Media to Collection
* Tagging Media in a Collection
* Tagging Collection
* Sharing Collection
* Sharing Item in Collection
