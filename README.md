# react-native-static-images
[![npm version](https://badge.fury.io/js/react-native-static-images.svg)](https://badge.fury.io/js/react-native-static-images)

Generate a file for using static images in react native.

## Install

```
npm install react-native-static-images --save-dev
```

## Usage

```
$(npm bin)/generate-images path/to/images --prefix ../ > src/Images.ts
```
Additional keys:

| Key | Description | Default |
| --- | --- | --- |
| --js | generate JavaScript code | TypeScript |
| --flow | add @flow comment, (--js key is assumed implicitly) | TypeScript |
| --indent (count) | number of spaces to use for indentation | 4 |
| --singlequote | use single quotation marks | double quotation

Full example:
```
$(npm bin)/generate-images path/to/images --prefix ../ --js --indent 2 > src/Images.js
```

## Example

```
$ ls public/images/
ResetPassword.jpg	SignIn.jpg		SignUp.jpg		challenges		movements		no-profile-pic.jpg	selfie.jpg
$ $(npm bin)/generate-images public/images --prefix ../ > src/Images.ts
$ cat src/Images.ts
export default class Images {
    static readonly resetPassword = require("../public/images/ResetPassword.jpg");
    static readonly signIn = require("../public/images/SignIn.jpg");
    static readonly signUp = require("../public/images/SignUp.jpg");
    static readonly challengesLegflowPicture = require("../public/images/challenges/legflow/picture.jpg");
    static readonly challengesLegflowThumbnail = require("../public/images/challenges/legflow/thumbnail.jpg");
    static readonly movementsPauseThumbnail = require("../public/images/movements/pause/thumbnail.jpg");
    static readonly movementsPushUpsThumbnail = require("../public/images/movements/push-ups/thumbnail.jpg");
    static readonly movementsSquatHoldThumbnail = require("../public/images/movements/squat-hold/thumbnail.jpg");
    static readonly movementsSquatJumpsThumbnail = require("../public/images/movements/squat-jumps/thumbnail.jpg");
    static readonly noProfilePic = require("../public/images/no-profile-pic.jpg");
    static readonly selfie = require("../public/images/selfie.jpg");
}
```
