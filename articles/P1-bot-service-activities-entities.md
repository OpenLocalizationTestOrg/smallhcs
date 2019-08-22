---
title: Entities and activity types | Microsoft Docs
description: Entities and activity types.
keywords: mention entities, activity types, consume entities
author: ivorb
ms.author: v-ivorb
manager: kamrani
ms.topic: article
ms.service: bot-service
ms.subservice: sdk
ms.date: 03/01/2018
---
# Entities and activity types

Entities are a part of an activity, and provide additional information about the activity or conversation.

[!include[Entity boilerplate](includes/C1-snippet-entity-boilerplate.md)]

## Entities

The *entities* property of a message is an array of open-ended <a href="http://schema.org/" target="_blank">schema.org</a>
objects which allows the exchange of common contextual metadata between the channel and bot.

### Mention entities 

Many channels support the ability for a bot or user to "mention" someone within the context of a conversation.
To mention a user in a message, populate the message's entities property with a *mention* object.
The mention object contains these properties:

| Property | Description |
|----|----|
| Type | type of the entity ("mention") |
| Mentioned | channel account object that indicates which user was mentioned | 
| Text | text within the *activity.text* property that represents the mention itself (may be empty or null) |

This code example shows how to add a mention entity to the entities collection.

# [C#](#tab/cs)
[!code-csharp[set Mention](includes/code/C1-dotnet-create-messages.cs#setMention)]

