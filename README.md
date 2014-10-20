Meteor wrapper for the Google Contacts API.

# Install

  mrt add google-contacts

# Usage
```javascript
var gcontacts, opts;

opts = {
  email: userEmail,
  consumerKey: googleId,
  consumerSecret: googleSecret,
  token: googleAccessToken,
  refreshToken: googleRefreshToken
};

gcontacts = new GoogleContacts(opts);

gcontacts.refreshAccessToken(opts.refreshToken, function(err, accessToken) {
  if (err) {
    console.log('gcontact.refreshToken, ', err);
    return false;
  } else {
    console.log('gcontact.access token success!');
    gcontacts.token = accessToken;
    gcontacts.getContacts(function(err, contacts) {
          // Do what you want to do with contacts
          // console.log(contacts);
    });
    return gcontacts.getPhoto(contact.photoUrl, function(err, binaryData) {
      // Save binaryData to your DB or file.
    });
  }
});
```
