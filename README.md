# CLRecipe - Social Media Recipes for TinCan API (xAPI)

The [Connected Learning Analytics Toolkit](https://github.com/kirstykitto) imports social media associated with a learning activity into an LRS and performs advanced analytics. The recipes to model social media interaction as xAPI statements are shared for community contribution and feedback. Recipes for Microblogging, Content Authoring, Content Collaboration and Content Curation will be provided.

Todo List:
- [ ] Add content curation, content authoring and collaborative authoring examples
- [ ] Add Contribute.md to outline how to contribute to project
- [ ] Add examples as .json files
- [ ] Register and get recipe id for recipe

## Modeling Social Media Interaction as an xAPI statement

The CLRecipe project:
*  maps terminology from various social media platforms to a common set of objects and verb
*  provides an xAPI Recipe for building xAPI statement for modeling social media interactions that include the relationship between social media posts (i.e. reply, share and like) so that advanced analytics (including content analysis and social network analysis) can be performed
*  provides xAPI recipe examples for:
  * Microblogging
  Microblogging occurs on platforms such as Twitter and Facebook where users are only allowed to post a short note with an enforced character limit.
  * Content Authoring
  Content Authoring refers to any long text that is written by a single user. A blog post make on Wordpress is an example.
  * Content Collaboration
  Platforms such as MediaWiki and Google Docs support content collaboration. On these platforms multiple authors are able to add, edit and delete content.
  * Content Curation
  Content Curation involves creating a collection of artefacts (e.g., documents, audio, video, images, etc).

Though social media platforms use different terminology, a common model of interaction exists (see figure below). The model involves:
* A user can create a post.
The post could be a short microblog post or a full article.
* A user can optionally including tag/s, hashtag/s or mention other users when creating the post.
* Other users can share a post (i.e. for their followers to view) and optionally including a comment.
* Other users can replying to the original post.
* Other users can rate the original post.

![Social Media Model](https://github.com/kirstykitto/CLRecipe/blob/master/socialmediamodel.png)

The Recipe for representing social media activity as xAPI statements prescribes that:
* A common set of verbs and objects must be used to represent activity across all social media platforms. Terminology used by specific platforms like Twitter and Facebook is mapped to a standard set of object and verbs (e.g. A 'Tweet' and Facebook Timeline post will both be mapped to the Note object; Twitter 'Favorite' and Facebook 'Like' will be represented by the 'Like' verb).
* A distinction between Short Microblogging posts (i.e. using the Note object) and larger text articles (i.e. using the Article object for pages and blog posts). This gives an indication of the size of the text included and is useful for content analysis (analytics).
* The social media platform must be specified using the *content.Platform* property. The inclusion of the platform (e.g. Twitter, Facebook, Blog, etc) will allow statement to be queried from the LRS based on the originating platform.  
* Tags, hashtags and @mentions that are included in a post must all be included in a single xAPI statement that represents the original post. There were two options to achieve this namely using  *context.contextActivities.Other* or *context.contextActivities.Category*. *context.contextActivities.Other* was selected because tags, hashtags and mentions represent folksonomies created by the user. *context.contextActivities.Category* is more suitable for use by custom taxonomies that are created at a system level for enhanced reporting (e.g. Cognitive Presence tagging, Sentiment Analysis, etc).
* Shares and likes must include a reference back to the object being shared or liked using *contect.contextActivities.Parent*. If the referenced id does not exist in the LRS it can be inserted using a substatement to represent the object. *contect.contextActivities.Parent* was chosen over using a *statementref* because because *contect.contextActivities.Parent* represents a direct parent-child relationship which required for social network analysis.
* Imported social media harvested from a group discussion area (i.e. Google+ Group or Facebook Group) must include *context.Team*.

Option additions to the recipe to facilitate reporting by course and instructor include:
* Imported social media should be associated with a course using *context.contextActivities.Grouping*.
* Imported social media should be associated with an instructor using *context.Instructor*.

### Activities

Activities are items that are created on social media platforms. Blog posts, tweets, homepage posts and curated media are all example objects. The CLRecipe makes a distinction between short Microblogging posts (i.e. using the Note object) and larger text articles (i.e. using the Article object).

| Activity  | Description | Source |
| ------------- | ------------- | ------------- |
| Note  | Represents a short-form text message. This object is intended primarily for use in "micro-blogging" scenarios and in systems where users are invited to publish short, often plain-text messages.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#note) |
| Article | Represents objects such as news articles, knowledge base entries, or other similar construct. Such objects generally consist of paragraphs of text, in some cases incorporating embedded media such as photos and inline hyperlinks to other resources.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#article) |
| Comment | Represents a textual response to another object. Objects of this type MAY contain an additional inReplyTo property whose value is an Array of one or more other Activity Stream Objects for which the object is to be considered a response. | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#comment) |
| Collection | Represents a generic collection of objects of any type.  | [Activity Stream Schema](http://activitystrea.ms/head/activity-schema.html#collection) |
| Audio | Represents audio content of any kind.  | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/audio) |
| File | Represents any form of document or file. | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/file) |
| Image | Represents a graphical image.  | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/image) |
| Video | Represents video content of any kind. | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/video) |
| Link | The URL to another resource.   | [Activity Stream Schema](http://adlnet.gov/expapi/activities/link) |


The table below show how social media activities from different social media platforms map to the Activities chosen for use by the CLRecipe.

| Platforms  | Note | Article | Comment | Collection |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Twitter - Tweet | Yes |  |  |  |
| Facebook -  | Yes (Post) | Yes (Page)  |  | |
| Blog Post | | Yes  | Yes | |
| Pinterest | |  | Yes | Yes |

### Verbs

Verbs are actions that are performed on an object. Most of the verbs used in the CLRecipe are from the [Activity Stream API](http://activitystrea.ms/head/activity-schema.html#verbs)

| Verb  | Description | Source |
| ------------- | ------------- | ------------- |
| Create  | Indicates that the actor has created the object.  | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/create) |
| Like  |  Indicates that the actor marked the object as an item of special interest. The "like" verb is considered to be an alias of "favorite". The two verb are semantically identical. | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/like) |
| Share  | Indicates that the actor has called out the object to readers. In most cases, the actor did not create the object being shared, but is instead drawing attention to it.  | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/share) |
| Tag  | Activity generally used in the "other" or "grouping" Context Activities lists to mark a statement as being related to a particular subject area. Implemented as a one word identifier used for search filtering or tag cloud generation. Includes hashtagging for tweets. | [TINCAN API](http://activitystrea.ms/schema/1.0/tag) |
| Rate  | Action of giving a rating to an object. In general the rating should be included in the Result with a Score object. There is an extension to include the 'raw' value as well as 'min' and 'max' range indicators. | [TINCAN API](http://id.tincanapi.com/verb/rated) & [TINCAN Quality Rating Extension](http://id.tincanapi.com/extension/quality-rating) |
| Add  | Indicates that the actor has added the object to the target. For instance, adding a photo to an album.  | [Activity Stream Schema](http://activitystrea.ms/schema/1.0/add) |

The table below show how actions from different social media platforms map to the Verbs chosen for use in the CLRecipe.

|   | Create | Like | Share | Tag | Rate | Comment | Add |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Facebook | Post | Like | Share | Tag | - | Reply | - |
| Google+ | Post | Like | Share | Tag | - | Reply | - |
| Twitter | Tweet | Favorite | Retweet | Hashtag | - | - |
| Blog | Post | - | - | Tag | Rate | Comment | - |
| Pinterest | Board | Like | Share | - | - | - | Pin |

An example xAPI statement based upon CLRecipe is provided below. The example is for a Twitter tweet that includes hashtags and mentions:

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

## Comprehensive CLRecipe Example xAPI Statements

Examples xAPI statement are provided for:
* [Microblogging](https://github.com/kirstykitto/CLRecipe/blob/master/microblogging_examples.md)
* [Content Creation](https://github.com/kirstykitto/CLRecipe/blob/master/contentauthoring_examples.md)
* [Collaborative Content Authoring](https://github.com/kirstykitto/CLRecipe/blob/master/collaborativecontentauthoring_examples.md)
* [Content Curation](https://github.com/kirstykitto/CLRecipe/blob/master/contentcuration_examples.md)
* [Association with Course, Team and Instructor](https://github.com/kirstykitto/CLRecipe/blob/master/associationwithcourseteaminstuctor_examples.md)

## Useful TinCan API Recipes
* [SCORM to Tincan API Cookbook](http://tincanapi.com/scorm-to-tin-can-api-cookbook/)
* [xAPI community of practice for user generated course content (UGCC)](https://github.com/ht2/UGCC-CoP)
* [xAPI Community of Practice for Mozilla Open Badges](https://github.com/ht2/UGCC-CoP)
* [Verbs and Activity Types used in Curatr](http://www.curatr3.com/admin-guide/#document-12)

## References
* [xAPI Specification](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI.md)
