# Criterion B: Solution Overview

## Record of tasks

| Planned Action | Details | Time (hours) | Date | Criterion |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|--------------|------------|-----------|
| Kick-off client/advisor consultation | Discussed overall goals of the product with the client and what features they wanted included. | 1.00 | 06/01/2016 | A |
| Research open-source technology | Found details and made notes of what open-source software I could use to develop this app. Adjusted expectations where appropriate. | 2.00 | 07/01/2016 | A |
| Client proposal | Shared research with client in the form of a proposal, received additional feedback that needed to be considered. | 1.00 | 08/01/2016 | A |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
| **Total** |  | 100.00 |  |  |

## Design
> Rundown of the classes, components etc. and UI Design, animations.
  Also need to describe how everything was tested (ie. unit testing, manually)

This product needed to be separated into two. The *backend* deals with running the server, and accessing a database through a RESTful API. The *frontend* is the app that runs on the mobile device, it is what the end-user interacts with.

### Backend

#### Models

Models are essentially a group of properties that get stored in the database.

An example of a model would be a `Spot`, this table represents all the properties:

| Property | Type | Description
| --- | --- | --- | ---
| `type` | `String` | Specify how to display this Spot. One of `photo`, `video`, `mixed` or `location`.
| `title` | `String` | Title of the Spot.
| `caption` | `String` | Description of the Spot.
| `photo` | `Photo.id` | Reference to a Photo record.
| `url` | `String` | Web URL of Spot that can be used to share on external services.
| `car` | `Car.id` | Reference to a `Car` record.
| `spotter` | `User.id` | Reference to a `User` record. This usually gets populated on requests.
| `created` | `Date` | When the record was created.
| `viewsCount` | `Number`| How many times the Spot has been viewed by a unique user.
| `likesCount` | `Number`| Amount of times the spot has been liked.
| `modified` | `Date` | When the record was last updated.
| `likes` | `Likes.id` | Reference to a `Likes` record.
| `location` | `Object` | Location object, contains latitude, longitude, altitude, city and country.

Each model can develop relationships by including references to other models, this can been seen above with the `photo`, `car`, `spotter`, and `likes` properties.

As an example, the `User` model represents a mix of both compositional and aggregational relationships.

![User Model Tree](https://dl.dropboxusercontent.com/u/61518573/locus-diagrams/user-horizontal-tree.svg)

The above diagram can be described as:

- A `User` does not depend on a parent association. Each can exist with 0 to an infinite amount of `Spot` references.
- A `Spot` cannot exist without a reference to a parent `User`. Each can have 0 to an infinite amount of `Comment` references.
- A `Comment` cannot exist without a reference to a parent `Spot`. Each can have 0 to an infinite amount of `Reply` references.
- A `Reply` does not depend on a `Comment` parent association, but does depend on a parent `Spot`. There are no child associations.

Many models within the product share similar relationships.

#### RESTful API Routes

### Frontend

#### User Interface

#### Components

Word Count: 