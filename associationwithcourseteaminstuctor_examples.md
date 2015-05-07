# CLRecipe - Social Media Recipes for TinCan API (xAPI)


## Associating Social Media Statement with a Course, Team (or Group) and Instructor
* Associating with an Instructor
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
      "name": "Aneesha Bakharia",
      "mbox": "test@mail.com"
    },
    "platform": "WordPress",
    "contextActivities": {}
  }
}
```

* Associate with a Team or Group
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
    "team": {
      "name": "Tut Group 1",
      "objectType": "Group"
    },
    "contextActivities": {}
  }
}
```
