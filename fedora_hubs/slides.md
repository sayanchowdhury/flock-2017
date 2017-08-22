---
title: Fedora Hubs 
separator: <!--s-->
verticalSeparator: <!--v-->
revealOptions:
    transition: fade
---

# Fedora Hubs
### A walkthrough the project

<!--s-->

#### What we are going to cover?

- What is Fedora Hubs?
    - Why are we building Fedora Hubs?
    - Defining the Fedora Hubs project
    - What is the goal behind Fedora Hubs?
- Architecture of Fedora Hubs
    - Basic Architecture of Hubs
    - Widgets: How can we build widgets?
- The Road Ahead!
- How can I help?
- When & Where do we meet?
- Questions

<!--s-->

### What is Fedora Hubs?
#### Why are we building Fedora Hubs?

- 

<!--s-->

### What is Fedora Hubs?
#### Defining the Fedora Hubs project

- include the from Hubs post by mizmo

<!--s-->

### What is Fedora Hubs?
#### What is the goal behind Fedora Hubs?

<!--s-->

### Architecture of Fedora Hubs
#### Basic Architecture of Hubs

- include the diagram from the docs to explain

<!--s-->

### Architecture of Fedora Hubs
#### Widgets: How can we build widgets?

<!--s-->

- Hubs core is based on the `Widgets Framework`.
- Encapsulates the common functionality to provide the Base class for the `Widgets`.
- Every components in the Fedora Infrastructure fits into Hubs environment as a `Widget`.
- The `Widgets` framework interacts with the external services such as Bodhi, Badges, Pagure.

<!--s-->

```
    from hubs.widgets.base import Widget

    class WorkshopWidget(Widget):

        name = "workshop-widget"
        position = "both"
```

<div style="font-size: 0.35em">ref - https://docs.pagure.org/fedora-hubs-widget-workshop/simple.html#basic-code-structure</div>

<!--s-->


```
class BaseView(RootWidgetView):

    def get_context(self, instance, *args, **kwargs):
        # Return the context to send to the template
        return dict(text=instance.config["text"])
```

<div style="font-size: 0.35em">ref - https://docs.pagure.org/fedora-hubs-widget-workshop/parameters.html#update-the-view</div>

<!--s-->

```
from hubs.widgets.caching import CachedFunction

class GetReviews(CachedFunction):

    def execute(self):
        # Perform the repeated steps to be cached.
        # The value is cache until the cached is not
        # invalidated.
        return [self]

    def should_invalidate(self, message):
        return False
```
<div style="font-size: 0.35em">ref - https://docs.pagure.org/fedora-hubs-widget-workshop/caching.html#writing-a-cached-function</div>

<!--s-->

### The Road Ahead (1/2)

- Release Hubs to production.
- Release Hubs for different teams within Fedora.
    - The first few teams being:
        - Design
        - Ambassadors
        - Websites

<!--s-->

### The Road Ahead (2/2)

- The next widgets to be released over next few months
    - Translation
    - Meeting
    - Regional Hubs
- Focus on the Fedora Hubs contributors
    - A weekly/bi-weekly blog post with the updates on the project.
    <include what OpenStack folks are doing to increase the contributions>

<!--s-->

## How can I help?

There are various areas to contribute:

- Build Widgets for Hubs.
- Triage issues for Hubs.
- Documentation for Hubs.
- Design widget for Hubs.
- Connect teams for Hubs.

<!--s-->

### When & Where do we meet?

We hang around in `#fedora-hubs` channnel.

Every Tuesday, we meet for the IRC meeting on the `#fedora-hubs` channel at 1400 UTC.

<!--s-->

### Questions

<!--s-->

Sayan Chowdhury
yudocaa@fedoraproject.org   
<br/>
Aurelien Bompard @abompard  
abompard@fedoraproject.org  
<br/>
Mairin Duffy @duffy  
duffy@fedoraproject.org

