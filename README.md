# Ada Web Developer Challenge

Hello there! :wave:

This is our challenge for potential new web developer team members. We'd like to see how you tackle an open-ended project in the growth & web development domain. We don't mind what language you use to complete the challenge. Feel free to try something new, or to use a technology that you're already comfortable with.

## Your Quest

We'd like to you design and build a simple micro-website responsible for a few things:

1. Data collection (gather name, email, number of support tickets / month, and average cost of a support request)
2. A "calculator" that calculates how much money a pospective client can save using Ada
3. A report (text file) that gets filled with the results of the calculator, as well as the data collected in step 1
4. A "success" page that has a link to download the report

When you're done, please open a pull request in this repository and we'll take a look! Expect us to give some feedback and ask questions to better understand your thought process.

### Important Notes

- Please don't spend too long on this! Please spend less than 1 working day.
- Please reach out to anson@ada.support or nick@ada.support if you have any questions! This should be fun and not stressful
- We intentionally left things ambiguous so that you can be creative. If you'd rather have things specified more closely, we are happy to provide guidance. Just ask!
- Feel free to use any technology and programming language that you'd like

### Specifications

Your solution should start a web server on any port you'd like. Please include instructions on how to start your server (so that we can test the functionality).

### Data Collection page

This is a simple web form that asks the user for:

- Name (first and last)
- Email
- Average number of support tickets they get per month
- Average cost to close a support ticket

The form should `POST` the data to your web server when the user clicks the `submit` button.

### Calculator

The calculator accepts the `form` data from the [Data Collection Page](#data-collection-page), and does a simple calculation to find the average money saved per month by using Ada.

The calculation is as follows:

`money_saved = tickets_per_month * cost_per_ticket * 0.2`

Here's an example:
```python
tickets_per_month = 10000
cost_per_ticket = 1.2  # in USD

money_saved = tickets_per_month * cost_per_ticket * 0.2

print(money_saved)

=> 2400.0
```

### Report Generation

Once you've determined the `money_saved`, we want you to inject the collected data, as well as the calculated data, into a report. Here's a sample report (feel free to use this text exactly).

```txt
Hey there {{ full_name }}!

Our goal at Ada is to provide an AI application for customer support teams that is simple to use, quick to deploy and highly accurate. To hit each of these checkpoints, the artificial brain powering our platform has to be a specialist. Why? While generalists can do a lot of things well, specialists have mastered their craft. By offering this level of expertise behind the scenes, we give our clients the freedom to focus on their craft, interacting with customers in front of the curtain.

You indicated that you have {{ tickets_per_month }} users, costing {{ cost_per_ticket }} each.

That means if you started using Ada next month, you'd save about {{ money_saved }}!

That's a lot of cheddar!

Contact sales for more details.
```

This report should render the client's full name, with correct capitalization. It should also render currencies correctly (using the locale of the browser).

### Success Page

The success page is the last page the client will land on. It should display a simple thank you message, as well as a link to where the report can be downloaded.

## Clarifications
- Feel free to use any language / framework that you choose
- Assume that the cost per ticket is in USD
- We highly recommend validating the incoming data (in the browser, on the server, or both)
- Please give us instructiosn on how to start and view the web site in the PR!
