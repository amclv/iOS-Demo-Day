# iOS Demo Day

## Requirements

1. Fork and clone the repository
2. **Add your presentation content**
    1. Slide deck (4 required slides)
    2. Links
    3. Answer all questions 
    4. YouTube demo video (1-2 min max)
3. Polish your Github Code repository
    1. Add screenshots and an overview to your GitHub Code Repository
    2. You should make that repository the "Public Portfolio" for your project
    3. Look at [John Sundell's Splash project](https://github.com/JohnSundell/Splash) for inspiration (code, images, GIFs)
4. Create a pull request (PR) and **tag your TL and Instructor**

## Links

* Github Code: `https://github.com/amclv/Inside-Mortgage-Calculator`
* Github Proposal: `https://github.com/amclv/ios-build-sprint-project-proposal`
* Trello/Github Project Kanban: `https://trello.com/b/ccWc1xR5/home-mortgage-calculator`
* Test Flight Signup (Recommended): `insert beta signup link here`
* YouTube demo video (Recommended): `insert video url here`

## Hero Image

`https://ibb.co/vqGmLRP`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    `Definitely has to be the math portion, something that may seem easy but math in code is definitely a little more challenging on the brain!`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    `The calculation for monthly payments. As I was working on them I kept getting 1.8333% rate when it was supposed to be 1.00833% rate. After constantly thinking and stepping away from the computer and messing with rate calculations on my phone. I realize that the calculation was missing one important thing...dividing by 100. Than came the power to the negative portion!`
  
3. Share a chunk of code (or file) you're proud of and explain why.

    `This portion of my code was using power negative to the term life which can be negative to the 180 or 360 power.`
    ```
    func createMonthlyPayments(with homePrice: Double?, downPay: Double?, annualRate: Double?, termLife: Double?) -> String {
        guard let unwrapHomePrice = homePrice,
            let unwrapDownPayment = downPay,
            let unwrapAnnualRate = annualRate,
            let unwrapTerm = termLife else { return "0" }
        
        let annualRate = max(0.00001, unwrapAnnualRate)
        let principle = unwrapHomePrice - unwrapDownPayment
        return currencyFormatter(xxx: Double(principle * ((annualRate/100) / 12)) / (1 - pow(1+((annualRate/100)/12), -unwrapTerm)))
    }
    ```
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    `I hear your trying to buy a house! You don't know where to start? Well..check out this elegant app!`
    `Don't know if you can afford a house? I understand, it can make your life stressful. Try this app out it! It will show you your monthly payments at a specific rate and help determine which house to buy.`
  
5. What is your #1 feature?

    `If I could use API calls, it would of been the Rates Tableview that displays current days mortgage rates based off banks. But for now I would say the calculater!`
  
6. What are you future goals?

    `I would like to get a graph or some type of a better visual to engage the users. Be able to use an API call to get current date mortgage rates.`

## Required Slides (Add your Keynote to your PR)

1. App Name / Team Slide
2. Elevator Pitch
3. Your #1 Feature (Customer facing — what can I do with your app?)
4. Future Goals

## Slide Requirements

1. 50 pt font minimum
2. Be concise — don't write sentences/paragraphs (put these in your slide notes for speaking)
3. 3-6 bullets maximum per slide
4. Do the squint test (can you read the text if you squint, if so, make the font bigger)
6. Images are always welcome
7. Do the Grandma Test (Would your Grandma understand you?)

### Optional Slides

1. Blooper: What's a funny bug or blooper? (screenshots/GIFs please)
2. Revenue Model: If the app was your sole source of income, how would you monetize it?

## Presentation Format

**7 minutes/team**

* 4 minute presentation (5 minute hard cap)
* 3 minutes of questions

We have ~12 teams presenting today — please practice your presentation with a timer (as a team), and make sure you fit within the time limit.

Plan on having one person present the slides and live demo. Please practice your presentation in front of a mirror or with your team 2-5 times. Have the app running and visible (Simulator or QuickTime) so you can quickly transition between slides and live demo.

* App Name / Team Slide (30 seconds)
* Elevator Pitch Slide (30 seconds)
* Your #1 Feature (30 seconds)
* Live Demo (2 minutes)
* Future Goals (30 seconds)
* Questions (3 minutes)
