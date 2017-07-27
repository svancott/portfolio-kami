---
layout: post
title: Know your role...
thumbnail-path: "img/logo_whozou.png"
short-description: Working as a Ruby on Rails Developer for Whozou.
---
{:.center}
![]({{ site.baseurl }}/img/logo_whozou.png)

**_Whozou?_** is a company that combines career alignment with personal development. Its foundation is built on a model that the company's founder created about 20 years ago. Ever since, he's been applying it successfully in his non-profit organization and has now decided to launch a for profit side. I work here as Ruby on Rails Developer and absolutely love it!

I get to build a lot of features and have really been able to add my touch to various parts of the site including:

  * Creating a custom payment solution with _Stripe_
  * Combining Rails and Ajax for adding real-time messaging system
  * Enhancing security with user permissions and filters
  * Using CSS, Bootstrap and Sass to build rich UI's
  * Developing widgets with Javascript and jQuery

**_Stripe_**:

For those who don't know, _Stripe_ is a software platform for accepting payments. They are the self-called "New standard in online payments". I don't know about all that, but they're software is pretty awesome. We decided to go with _Stripe_ for accepting payments on **Whozou** and it was my responsibility to integrate it. Since I used _Stripe_ in a previous app of mine, ([Vanipedia](https://vanipedia.herokuapp.com/)), I was already familiar with it. In [Vanipedia](https://vanipedia.herokuapp.com/), when you sign up for a new account you're able to create custom wikis and collaborate with other users of your choice, but those wikis will be public. To create private wikis you need to be a _Premium Member_. You can go to your profile, click "Upgrade to Premium", and there you'll find the _Stripe_ API. For that app, I used the default API and formatting it was relatively quick to implement.

In **Whozou**, a few things needed to be different than _Stripe_'s standard API, so I had to create a custom payment solution. First, I formatted the css of the API to match our site's style. Next, we wanted users to be able to sign up for the services of their choice and be able to pay for them in one step, so I needed the payment modal to appear on the sign up page (with the default _Stripe_ API, this would be two steps). Lastly, I made it so that the payment modal was pre-populated with the information from the user's sign up so they wouldn't have to enter it again; things like email and name. Once, a successful payment is validated, the ```create``` action is called in the ```UsersController``` and the user is successfully created and stored in the database.

The path from choosing options to sign up to payment is quick, painless, and snazzy, and owner of the company was thrilled with my work. In my next post, I'll talk about how I combined Rails with Ajax for a  lightening fast messaging system (spoiler-alert: ```remote: true```). See you next time!
