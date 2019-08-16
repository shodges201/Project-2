# KEEP IT LOCAL®

KEEP IT LOCAL® is a tool to help people better connect with their local communities. 

KEEP IT LOCAL® is a tool for independent creatives to build scenes and find audiences.

KEEP IT LOCAL® is an echo chamber to remind you of reality.

KEEP IT LOCAL® is for the kids.


New users sign up with just a username and password, no additional personal information is stored. Each time they log on, they are asked for their current location and are shown all the events coming up in their area. Joining the network is referral-only. To build trust across the platform, we must ensure that a user is both in the local area and a mutual friend of someone in the network. To combat spammers, new users must wait 3 days initially before getting referral codes to pass to friends. After that, users can generate a new code every 3 days. Users can browse events and post messages anonymously while tapping into the different pockets of culture bubbling in their town. 


[Try out the beta](https://keep-it-local.herokuapp.com/) using the below guest login.

username: localhost8080
password: localhost8080


## Features

* Anonymously post and promote local events
* RSVP to and leave messages on events
* Refer your friends

## Generating Referal Codes

In order to be able to be apart of the Keep It Local network, you must first be invited by a current users's Referal Code. Once you have created your own profile, you will be given your own Referal Code that will change every 3 days.

```js
app.post("/api/code", function (req, res) {
    db.ReferralCodes.create({
      creatorID: req.user.userName,
      code: voucher_codes.generate({
        length: 8,
        count: 5
      })[0]
    }).then(function (resp) {
      console.log("code created");
      console.log(resp);
      res.json(resp);
    })
  })
```

## Built With

* [Materialize](https://materializecss.com/) - Web Framework
* [Handlebars](https://handlebarsjs.com/) - Templating
* [Moment](https://momentjs.com/docs/) - Library for parsing, manipulating time values
* [Passport](http://www.passportjs.org/) - Login Authentication for Node.js
* [Geocoder](https://developer.mapquest.com/documentation/geocoding-api/) - Library for geocoding via MapQuest API


## Team Members
* Zubin Mulji
* Lance Toledo
* Scott Hodges
* Quinton Smith

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
