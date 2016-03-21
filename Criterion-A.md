# Criterion A: Planning

## Description of Scenario

The client for this product is a aquaintance of mine. They run their own business photographing rare and exotic cars around the world. The client was very proud of his work and wanted to share it with the rest of the *automotive enthusiast* world.
He ran into issues using the photo sharing apps out there today – none of them directly catered to the audience he wanted to target.
Knowing I had experience building digital products, the client came to me for ideas on how to solve this problem. We decided that a mobile automotive photo sharing app would solve this problem.

## Rationale
> How problem was solved, why I decided to use certain tools

## Criteria for Success
> What is needed to solve the problem

### Requirements
- A database that stores all information alongside relationship association; Users can be associated to many Spots and Spots can only be associated to a single user.
- A back-end API service that acts as a link between the front-end interfaces and the database. Every record has to be able to be read, created, updated and deleted.
- An app interface that runs on the latest version of Apple's iOS and provides a straight-forward user experience that could easily be translated to other platforms (Android and Web).
- Camera view that allows a user to take a photo with location data, save it to the device's photo library and then be able to upload it to an external server.
- Asynchronous storage on the device that can store cached data such as the logged in user. Doing so would allow as few backend requests to be made as possible.
- Users should be able to create Spots with a title, caption and location.
- Users should be able to *like* Spots, and *follow* other users.

### Extras
- Develop a web interface that can be accessed through browsers.
- Allow users to save other types of media other than just images (ie. looped videos, slideshows).
- Third-party service integration; Allowing users to upload media from external services like Dropbox or Google Drive.
- An interface where a user can make modifications to an image like cropping, adding filters etc.
- Private messaging between users.
- Searching feature that would allow users to search the entire database for certain Spots or other users that match a specified query.
- Allow Users to make comments on Spots and reply to other comments.

Word Count: 