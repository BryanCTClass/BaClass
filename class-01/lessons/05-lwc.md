# Lesson 05 — Lightning Web Components

## What Is an LWC?

A Lightning Web Component is a reusable UI block built with standard HTML, JavaScript, and a Salesforce-specific metadata file. They live on record pages, app pages, and anywhere in the Salesforce UI.

## File Structure

Every component is a folder with three files:

```
lwc/
└── speakerCard/
    ├── speakerCard.html          ← template (what it looks like)
    ├── speakerCard.js            ← controller (what it does)
    └── speakerCard.js-meta.xml  ← metadata (where it can be used)
```

## Demo Component: speakerCard

A simple card that displays info about a SoundCraft speaker model.

**speakerCard.html**
```html
<template>
    <lightning-card title="Speaker Model">
        <div class="slds-m-around_medium">
            <p><strong>Model:</strong> {modelName}</p>
            <p><strong>Category:</strong> {category}</p>
            <p><strong>MSRP:</strong> {price}</p>
        </div>
    </lightning-card>
</template>
```

**speakerCard.js**
```javascript
import { LightningElement, api } from 'lwc';

export default class SpeakerCard extends LightningElement {
    @api modelName = 'SoundCraft Pro 500';
    @api category = 'Studio Monitor';
    @api price = '$899';
}
```

**speakerCard.js-meta.xml**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
    <apiVersion>66.0</apiVersion>
    <isExposed>true</isExposed>
    <targets>
        <target>lightning__AppPage</target>
        <target>lightning__RecordPage</target>
    </targets>
</LightningComponentBundle>
```

## Deploy to the Org

```bash
sf project deploy start \
  --source-dir force-app/main/default/lwc/speakerCard \
  --target-org CTClass
```

Then go to App Builder in your org to add the component to a page.
