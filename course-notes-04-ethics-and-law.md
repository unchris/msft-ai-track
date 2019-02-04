Ethics and Law in Data and Analytics - Course Notes
============
January 2019
Chris Cameron

I am auditing [Microsoft Professional Program for Artificial Intelligence track](https://academy.microsoft.com/en-us/tracks/artificial-intelligence/).

The fourth of 10 courses is [Ethics and Law in Data and Analytics](https://courses.edx.org/courses/course-v1:Microsoft+DAT249x+1T2019/courseware/083e1ae3-93c7-1f72-6306-1765a78799e4/9858b654-cac7-48aa-978b-232e1bfe9cd0/1?activate_block_id=block-v1%3AMicrosoft%2BDAT249x%2B1T2019%2Btype%40vertical%2Bblock%40ff699a02-a439-e66f-5e3a-14a6ea2d4238).

# Before You Start

## Data's Ethical Foundations

### Ethics Foundations, Part 2

Ethics is the study of human well-being.

Values about Others
- Reduce Suffering
- Promote Autonomy
- Improve Equality
Values about Myself
- Promote my Virtue/Character
- Want peolpe to Trust me

### Ethical Foundations, Part 3

Data ethics is the study of how data affects human well-being.

### Further Reading

“Big Data: Seizing Opportunities, Preserving Values” (Executive Office of the President May 2014) U.S. Executive Office. https://obamawhitehouse.archives.gov/sites/default/files/docs/big_data_privacy_report_5.1.14_final_print.pdf

Crawford, Kate. “Big Data Gets Personal.” https://www.youtube.com/watch?v=JltwkXiBBTU

## Data's Legal Foundations

### Law, Analytics, and Society

Theme 1: Law is territorial / confined to territory that created it.

Law moves slowly and chases technology.

Theme 2: Strained relationship between law, data analytics, and AI.

There is not much law to regulate how data is collected, shared, and used.

Theme 3: Legal tension with respect to human rights and organizational rights.

### Different Types of Law

Three basic sources of US Law

1. Common Law (judge-made law)
2. Statutory Law
3. Constitutional Law

Common law is created by courts. In the US and former British colonies, judges have the authority to actually create rules of law that determine individual and organizational rights and responsibilities.

An example common law is negligence law. To study it, you research and review court decisions.

Statutory Law is created by representative bodies such as the US Congress. This law is proactively created to regulate individual and organizational behaviour.

An example is GINA passed by Congress to regulate genetic law not discriminating against people.

Constitutional Law comes from the constitution and gives the government the authority to act and restricts that authority to ensure that the branches don't overstep bounds or infringe unnecessarily on rights.

Some laws (like privacy) is sourced in all three kinds of law. Privacy Law can be found in common law in `privacy torts`, in statutory law in legislation like GINA, and in the constitution via amendments.

International law interacts with these sources of US law. E.g., UN Declaration of Human Rights. How they are binding is not the same as US Law, and where they are binding, it's only on the governments that signed, not private organizational parties.

### IRAC Analysis

IRAC: Issue, Rule, Application, and Conclusion

Traditional method for analyzing legal problems that arise in any context.

Interesting case to try IRAC with: 2012 Target knew about a teen's pregnancy before the parents and mailed her ads for baby stuff.

Issue: So what's the Issue or the Legal Problem in the situation? In this case, it might be stated as whether Target infringed on the teenager's rights by using data about her purchasing behavior to identify her as pregnant and then market to her.

Rule: What rules are relevant to the situation? It's an intimate situation, maybe privacy rights violation? Because Target is an organization, versus a part of the gov. subject to constitution, we would start by considering common law privacy torts to see if they are relevant. We may also check for statutes on point to protect her privacy interest.

Application/Conclusion: Unfortunately there were no privacy laws that protected her. Target used internal customer information and externally publicly available data. In applying the facts to the existing rules of privacy there is no breach, so the Conclusion is Target behaved lawfully.

That doesn't mean it was ethical though. Just because you _can_ do it, doesn't mean you _should_ do it.

### IRAC Continued

They give another example of IRAC

### More Reading

Smith, Brad. “Modern digital data laws that balance law enforcement needs with privacy can create a model for the world.” https://blogs.microsoft.com/on-the-issues/2017/06/15/modern-digital-data-laws-balance-law-enforcement-needs-privacy-can-create-model-world/

## Ethical Data Practice

### Subjective to Objective

He just keeps foreshadowing things that will be brought up in later modules. Name-drops ETL at least.

### A Data Oath

Examples of useful "oaths"

- UN 1985 Declaration for Statisticians
- Certified Analytics Professionals Code of Conduct

Dude's attempt at an oath:

> I as a data practitioner will promote the well-being of others and myself while striving to do no harm with data through:
> 1. Professional application of analytical techniques
> 2. Humility in analytic claims
> 3. Anticipation of legal and regulatory scenarios
> 4. Transparency in computation and documentation
> 5. Fidelity to this oath beyond the bottom line

### Ethical Data Use Cheat Sheet

I like how they worked "Ethical" and "Cheat" into the same sentence.

Anyway it's a screen capture of a page from an article I think, the reference given is:

Martin, Kirsten. “Ethical Issues in the Big Data Industry,” MIS Quarterly Executive, June 2015 (14:2)

### Further Reading

Schwab, Katharine. “Data Can Lie,” https://www.fastcodesign.com/3067315/data-can-lie-heres-a-guide-to-calling-it-out

## Lab

### Assignment

nothing

### IRAC Application

From a MS Case: Does the Stored Communication Act allow the US Government to obtain customer information stored in e-mail from computer service providers like Microsoft when the information is stored on servers and data centers that are outside of the physical territory of the United States.

Issue: Can the law apply outside the US?

Rules:
1. Stored Communication Act is inside Electronic Comms Privacy Act.
2. Presumption against extra-territorial activity of law
3. Morrison Decision recently was against extraterritorial application of US law

Application:
Though the SCA allows seizing data for surveillance and law enforcement, it cannot be used extra-territorially.

Conclusion: court said section 2703 of the SCA was not intended to extend beyond the United States

### Data Set Instructions

COMPAS - COrrectional Offender Management Profiling for Alternative Sanctions. This algorithm assesses a criminal defendant's likelihood to re-offend.

> You will be redirected to GitHub, a third party website whose privacy practices differ from Microsoft's. If you provide personal data, your data is governed by their privacy statements.

Funny since MS owns GitHub now and this notice is being printed on edx.org which is NOT owned by MS as far as I know...

They say to download a zip file but I'd rather clone it

### Explore the Compas Data Set

This video is half an hour => set playspeed to warp 9

excel correlation function tells you how correllated two columns are. if it's 1.0 it means the values are exactly the same. he does this to find out if he has useless data. he deletes the duplicate. neat

he's sayying when you get a spreadsheet of features like this, usually you get a seprate document called a "data dictionary" that explains what all the columns are because e.g. `v_type` means nothing to you

> So let's go to Bing, our trusty search engine

_sigh_

He looks up the definition of recidivism to know how long into the future they looked and what kinds of crimes counted (e.g, parking tickets don't count). COMPAS was made by Northpointe.

He's wondering whether any of the `features` is unethical to include, but frankly the use of this COMPAS tool _at all_ seems unethical.

He's going to use Pivot tables to see relationships between data. This seems dumb considering they spent other courses talking up using Jupyter for this.

uses race as row, decile_score as column and value. which tells you "by race what are the recidivism rates like". find sa correlation between african americans being more suspected of recidivism than caucasians.

makes another pivot table 'score_text' is a row (low/med/high), value set to count of priors, and then asks for the average instead of sum. finds a correlation between prior arrests and high recidivism.

### Exploration Prompt

This is a sheet of questions to use against the video just watched. The guy already went through it though in the video so I guess it's just to give you a hard-copy to refer to.

### Validation

The validation question isn't loading for me

### Module 01 Assessment

Unavailable due to Auditing

# Data, Individuals, and Society

## Data Bias and Identity

### Data, Individuals, and Society

Let's not allow data science, data analytics, and AI to take our right away to define ourselves.

### Bias in Data Processing - Part 1

Conscious Bias: one you're aware of

Unconscious Bias: one you're not aware of, but still affects your decision-making

We are worried about Machine Subconcious Bias.

Ways Bias Enter Data
1. Data Input is Biased

### Bias in Data Processing - Part 2

Ways Bias Enter Data
1. Data Input is Biased
2. Use of Irrelevant Data (bias in Feature Selection)

### Legal Concerns for Equality

- No transparency in data collection and use.
- No clarity about who is included and excluded from collection
  - Interesting thought: a person who lives "off-grid" so-to-speak becaues they can't afford, e.g., personal internet, cell phone, netflix, GPS, and so on, has a lower data footprint, and thus may experience 1. tangible economic detriment because businesses will undervalue their preferences, and 2. possibly exclusion from civil and political life because they're just not counted or considered
  - The Equal Protection Doctrine in the US protects against things like race, gender, ethnicity, but does not protect on the basis of e.g., economic worth or how often connect to Internet AND it only protects from actions taken by GOV, not private corps

### Bias and Legal Challenges

two challenges:
1. data inputs to algorithms
2. design of algorithms themselves

for challenge one,
- if the data input to a "fastest route" calculator only gets its data from smartphones, then it may cover "poor areas" of town worse
- if it only includes data about roads, but not bike routes or public transport, then it will exclude people who don't own a car

for challenge two I think a later video will tackle it

IP rights are in tension with individual rights to be free of discrimination

### Consumers and Policy

As many as 11% of consumers don't have enough history to get an algorithm-derived credit score. WOW.

Data analytics can improve this, but that doesn't protect for discrimination from bias.

Fair Credit Reporting Act and Equal Credit Opportunity Act may help here

### Employment and Policy

Hiring Practices use algorithms.

Civil Rights Act might help, but because of transparency problem, it's hard for anyone to realize discrimination might have occurred.

### Education and Policy

Improving student learning, retention and graduation. How?

Big Data could help reduce or produce discrimination.

Some universities already using data points to predict pathways to success.

Family Educational Rights and Privacy Act (FERPA) helps here.

A concern that students maintain autonomy and the right to self-determine a path of study consistent with their wants regardless of algorithmic diagnostic or predictions. Could be called "Right to Autonomy Privacy" or "Right to Identity Privacy".

### Policing and Policy

Criminal Justice and Predictive Policing

identify crime hot spots

- interesting: data from body cameras removes some subjectivity in police reporting

### Best Practices to Remove Bias

I'm short-handig this, but it comes from 2016 Obama executive report on Big Data and Bias

1. support research into mitigating algorithm discrimination, build systems with fairness, etc
2. encourage market to design best systems including transparency and accountability, and appeals processes
3. promote auditing and external testing to ensure fairness
4. broaden participation in computer science and data science including opportunities to improve fluency for everyone

### Descriptive Analytics and Identity

Descriptive and Predictive analytics are similar in that they both need aggregated data.

Predictive analytics tries to forecast future data

Descriptive analytics is used to describe the present or past

The problem of just saying nobody should have access to my data

"at least if they're going to find out a lot about me, I hope whatever they conclude is accurate"

this two-direction anxiety is analogized by Kate Crawford

> "We are worried that our data is like a harsh fluorescent light that shows both too much of us and not enough at the very same time, and therefore displays a false and unflattering picture of us"

Is there some part of your digital profile that's wrongly characterizing you and putting you on a list somewhere?

We need a chance to challenge these characterizations (appeal)

The providers argue that their algorithms might tell you things about you that you don't even realize.

No laws governing this space.

### Further Reading

Barocas, Solon, and Andrew Selbst. “Big Data's Disparate Impact,” California Law Review, 2016, Vol. 104:671

“Digital records could expose intimate details and personality traits of millions.” http://www.cam.ac.uk/research/news/digital-records-could-expose-intimate-details-and-personality-traits-of-millions

Pasquale. Frank. The Black Box Society: The Secret Algorithms That Control Money and Information. Harvard University Press, Cambridge Massachusetts: 2015 ed.

## Data Privacy and Power

### Privacy, Privilege or Right

- Decisional Privacy
  - right to be let alone wrt how we live our lives, who we partner with, raise children, medical treatments we accept/reject
  - most affected by gov actions that attempt to restrict full expression of privacy by citizens
  - e.g. in the US, attempts to restrict reproductive freedom
- Informational Privacy
  - the right to be let alone wrt information or data that reveals knowledge about us
  - social sec numbers, race ,gender, religion, health data, fitness level, genetic data etc
  - outside of constitutional protection against gov actions against privacy, most privacy law is buried by sector in US law
  - i.e., there's no overarching privacy rule
  - separate laws for protecting health data, financial data, student data, etc
  - the laws are very specific and they get stretched in their application
  - there's also common law that protects privacy in an area called "torts" which protect individuals from wrongs committed by another that caused physical financial and emotional harm

there seems to be a prevailing feeling that perhaps americans think of privacy as a privilege than a right, since they so freely give away info

### Privacy Law and Analytics

Statutory law comes up lots in Business
- HIPAA, GINA, FERPA, ECPA
Common Law - Torts - Intentional torts in privacy
- Intrusion into Seclusion
  - e.g., person peering into a women's dressing room
  - is misuse of people's data like fitbit an intrusion into seclusion?
- Appropriation of Name or Likeness
  - protects our identity, name, picture, etc
  - somebody taking a picture of a celebrity and selling it on a t-shirt
  - commercial advantage has to be established and their has to be an offensive use
- Public Disclosure of Private Facts
  - like disclosing someone has an infectious disease
  -
- False Light
  - it has to be publicly but a misalignment of who we are
  - taking a picture and putting them in a headline in a newspaper that says something that is false
  - can data falsely portray us? of course because of bias and bad data input

### Negligence Law and Analytics

Negligince law is state law, is common-law and is relevant to all kinds of behaviour personal and business.

1. duty
  - defender has a duty to act as a reasonable person under the circumstances
  - e.g., car driver must drive reasonably given conditions
2. breach
  - we breach that duty when we fail to act carefully
  - e.g, go way over the speed limit on a stormy day and cause an accident
3. causation
  - link between breach and the damages that are caused.
4. damages
  - physical emotional and/or financial damages
  - negligence is tort law, which protects us from these harms

This can include
- negligent product design, think about autonomous cars.
- negligent hiring
- negligent distribution - e.g., distributing guns in a less regulated area knowing they could end up in the black market
- negligent data collection or management?
  - there can be a claim that the data broker or the data user is collecting info in a way that's not careful enough
  - big data breaches involve negligence

### Power Imbalances

People > Government > Business is the ideal state but we know it's not like that all the time or at all

power in this sense means final authority, not complete control

Knowledge is power => Data is power

government has a ton of data on citizens, but not vice-versa, which is flipping the power structure here

government has to often ask or take the data from businesses, so the power structure is kind of reversing with Big Data

### Personal Data and Privacy

I copied this directly:

> Some questions to ask yourself when you find or have PII in your data set:
> - What are your company's needs around using these PII values?
> - Who needs access to this data?
> - Can you lock down access to those who need it, or is that not possible with your system?

### Masking Personal Data

Techniques to mask your personal data

- substitution:
  - e.g., putting 1234-5678-9012-3456 in for a credit card number
  - there's a risk that the substituted value could mean something too, or you lose the original reason for storing the value
- shuffling
  - e.g., taking pairs like (Sarah, 1), (Bill, 493), and (Sue, 661) then shuffling it around to (Sarah, 661), (Bill, 1), (Sue, 493)
  - danger is that the real data is still there and could be potentially re-associated
- number and date variance
  - essentially rot13 but even say with dates by shifting them forward or backward by some amount of time
  - it's still a proper date/number but no longer accurate
- encryption
- nulling out or deletion
  - you lose data integrity when you do this but it does wipe the data out
- differential privacy
  - using statistical methods to incorporate noise into all the records in a data set
  - they call out to the _Further Reading_ section

### Further Reading

“Big Data: A Tool for Inclusion or Exclusion? Understanding the Issues” (FTC Report January 2016) U.S. Federal Trade Commission. https://www.ftc.gov/system/files/documents/reports/big-data-tool-inclusion-or-exclusion-understanding-issues/160106big-data-rpt.pdf

“Big Data: A Report on Algorithmic Systems, Opportunity, and Civil Rights” (Executive Office of the President May 2016) U.S. Executive Office. https://obamawhitehouse.archives.gov/sites/default/files/microsites/ostp/2016_0504_data_discrimination.pdf

More on encryption: https://www.howtogeek.com/howto/33949/htg-explains-what-is-encryption-and-how-does-it-work/

More on differential privacy: https://privacytools.seas.harvard.edu/differential-privacy

## Lab

### Assignment

blank

### IRAC Application

4 minute video about applying IRAC again

facebook sponsored stories created ads with members' photos without their knowledge and consent

issue: did FB violate right to privacy using their photos like this?
rule: appropriation of name or likeness

application: mental distress of the person whose identity was used, or damage to their identity

My: conclusion: they violated their right ot privacy by appropriating name or likeness

Facebook settled out of court so we don't know for sure

### Personal Data Exercise

they ask you to try some of the data masking ideas from the _Masking Personal Data_ section after identifying which data might be considered personal in the COMPAS data set

### Validation

don't see the validation question

### Module 02 Assessment

n/a becaues auditing

# Data Ethics and Law in Business

## Business and Ethical Data Use

### Data Ethics and Law in Business

how is business regulated in data analytics and AI

european law as well

how will it be interpreted with new technology?

### Handling Consumer Data

FTC laws that help and two case examples

- Fair Credit Reporting Act
  - explains that Consumer Reporting Agencies have a specific duty to its clients

FTC decided that Spokeo became a CRA and subject to the FCRA rules, which they weren't following and fined $800k. This, even though Spokeo claimed on their website that they were not a CRA and users should not use their site for credit eligibility purposes, per se.

Organizations and participants in data analytics and AI should not assume that existing law does not regulate them.

Section 5 of the FTC to take enforcement actions for violations of consumer privacy rights.
- "unfair or deceptive acts or practices in or affecting commerce are unlawful"
- This affects companies that fail to secure, or to for sharing or selling data analytics products to customers who may use that data for fraudulent purposes
- TrendNet got in trouble with home security cameras that broadcast on the internet. Hackers compromised live feeds of people's homes and FTC brought action against TrendNet for not securing them

Recommendation: Read page 24 of 2016 FTC Report _Big Data - A Tool for Inclusion or Exclusion?_ which will help you road map legal compliance for customer concerns in the United States.

### Handling Employee Data

Main US Federal Laws for Employee Protection

1. Title VII of the Civil Rights Act of 1964
2. Americans with Disabilities Act (ADA)
3. Age Discrimination in Employment Act (ADEA)
4. Genetic Information Nondiscrimination Act (GINA)

Protected classes under Title VII
- race
- ethnicity
- national origin
- gender
- religion

Theories of Liability for Violations of Equal Opportunity Laws
- Disparate Treatment: an employee is treated differently based on a protected characteristic
- Disparate Impact: when employer's policies are facially neutral, but disproportionately impact a protected class. does not count if the policy or practice furthers a legitimate business need and cannot reasonably be achieved by means that have less disparate an impact on that class
  - (me: presumably this would be something like, firefighters having requirements to drag a human body X meters, which might disproportionately be more difficult for women? - they bring something like this up in the video too hah! or a requirement to speak english when maybe you're ESL from another country?)
  - this unintentional discrimination happens more often in analytics and AI

### Ethics in Hiring with Big Data

People Analytics / HR Analytics
- working on finding algorithms that don't dicsriminate in hiring, but still find ideal employee
- bias is still a problem
- can they find data that is a proxy for how good you are? instead of using employment history, which may not be fair data?
- what if an algorithm uses a six month employment gap as a proxy for something? we know it could be irrelevant, but does the algorithm know? transparency matters here

### Digital Market Manipulation

plenty of neat examples, here's two:
- makeup companies advertising the most on Mondays because women report feeling most unattractive on Monday morning.
- putting really expensive TVs on the shelf to make the one you're buying seem comparatively a good deal

Big data allows businesses to combine personalization and systematization.
- an example of this is when you buy a book and the seller recommends similar books
- previously personalization and systematization were typically separated on e.g., TV ads (systematization) or in a car dealership (personalization)
- this can be a win-win like with the books, but what if big data learns all about you and knows how to market tempting products to you when you're vulnerable?

### Further Reading

Calo, Ryan. “Digital Market Manipulation,” The George Washington Law Review, August 2014 Vol. 82 No. 4

De Romree, Henri, Bruce Fecheyr-Lippens, and Bill Schaninger. “People Analytics Reveals Three Things HR May Be Getting Wrong.” http://www.mckinsey.com/business-functions/organization/our-insights/people-analytics-reveals-three-things-hr-may-be-getting-wrong

Gee, Kelsey. “In Unilever's Radical Hiring Experiment, Resumes are Out, Algorithms are In,” Wall Street Journal. https://www.wsj.com/articles/in-unilevers-radical-hiring-experiment-resumes-are-out-algorithms-are-in-1498478400

## Business and Data Privacy

### The Evolution of Privacy and Technology

Been evolving since laws in US and Europe in 70s

Five Principles from the 70s
- Access to Stored Records
- Transparency of Process
- Control Options for Individuals
- Security
- ?? what's the 5th?

In the 90s there was another wave of legislation

Recently the GDPR and proposed Privacy Bill of Rights in the US

Push for Privacy by Design

### Data Privacy and Security Best Practices

Suggested best practices based on FTC's enforcement actions (they're sharing the highlights but you can go get a reprt)

1. Know Your Data - The FTC takes an expansive view as to the types of data it considers personal
2. Don't Avoid a 'Privacy By Design' Approach - build into your technology consumer privacy protections.
3. Do consider whether and how users should be provided notice and choice
4. Do have a privacy policy covering the IoT device and ensure it is accurate. No one US law for this but the FTC is monitoring it and some states have laws already (e.g. Cali)
5. Don't forget to update all representations to match your privacy practices
11. Do apply extra scrutiny when it comes to collecting sensitive data
15. Don't forget to monitor for new development sat the FTC

### GDPR

The EU's previous one was in 1994.

The GDPR allows for higher fines to actually cause changes

The EU really does not trust other jurisdictions to regulate data as protectively as the EU does.

GDPR
- Applies to more businesses than the 1994 privacy directive
- Applies extraterritorially too, as long as the company is processing data from EU citizens
- Definition of personal data has been expanded, including name, location, online identifiers and genetic info
- Non-compliance has severe penalties
- data controllers must notify supervisory authorities within 72 hours of a data breach
- new record-keeping requirements and ability to produce records on demand
- consent given by data subjects must be clear, freely given informed and specific and can be withdrawn at any time without consequences
- since GDPR is a regulation, there is only one version across the EU, whereas the privacy directive of 1994 had different implementations

questions you should ask:
1. what personal data does my company collect and store and how is it used?
2. do our activities fall within scope of gdpr?
3. do we meet the definition of a data processor or controller?
4. do we have a high level of responsibility for data security?
5. have we developed data breach response plan?

GDPR calls it Data Protection by Design/Default, believed to become a legal requirement.

### GDPR, Big Data, and AI

data protection principles that are threatened by use of Big Data and AI
1. big data analytics must be fair
2. you need permission to process
3. purpose limitation - don't use data inconsistent with what you tell users
4. holding onto data - minimize how much data you collect
5. accuracy
6. individual rights and access to data and ability to correct it
7. security measures and risk
8. accountability - erroneous algorithmic decisions based on biased profiling throw up issues here
9. controllers and processes - data controllers and data processors are different, make sure you know the definition

### Further Reading

“Are you ready for the EU's General Data Protection Regulation (GDPR)? Our two new tools can help you find out” Microsoft Corporate Blog. https://blogs.microsoft.com/on-the-issues/2017/07/17/ready-eus-general-data-protection-regulation-gdpr-two-new-tools-can-help-find/

Smith, Brad. “Keynote address, APP Global Privacy Summit 2016.” https://www.youtube.com/watch?v=BnxlSObym88

## Lab

### Assignment

nothing

### IRAC Application 3

Company A uses smartphone camera to analyze pupil for concussion symptoms. You've been hired at Company A to voice your concerns about any legal issues.

Issue - is there an issue of an invasion of privacy as a result of collecting this personal medical data?

Rule - HIPAA protects health data. HIPAA applies when an org plays a certain role in healthcare provision to patients. then, HIPAA applies also if the organization handles Protected Health Information (PHI). So, is it a covered entity or associate and handles PHI?

Application - no case law to look up here because it's so new. Who are the app's customers? Who directs use of the health data? does company A have formal relationship with covered entities? will a covered entity require the use of the app?

Conclusion - since the app is probably not working with a doctor's office or being one, and since the consumers have direct access to the data means HIPAA probably doesn't cover this, at least right now. New law may change this.

### The Ethics and Variables of Recidivism

Problem 1.

Hypothetical study shows human judges over-predict recidivism 30% of the time. A new algorithm over-predicts recidivism only 12.5% of the time

Is the algorithm better?

Further hypothetical study shows that Caucasian defendants went from 30% to 10%, but african-americans went 30% to 15%.

Is it still better? You have reduced the overall amount of unnecessary time in jail... BUT, the color of someone's skin is now MORE likely to determine longer time in jail.

Accuracy is important but it can't be traded for social justice.

Problem 2.

Why do we punish people?
1. Theory: Retributivism
  - justified and only if it is retribution for a past crime
  - problem: if the algorithm makes any mistakes, you have punished someone for an action that he had not committed (and never would have)
2. Theory: Rehabilitationism
  - Punishment is justified iff it is likely to rehab a criminal
  - Problem: the algorithm seem to be concerned with accurate predictions, not rehab
3. Theory: Consequentialism
  - punishment justified iff it brings about good consequences for society as a whole
  - thought experiment: what if we found an old, harmless, former serial killer? he can't re-offend because too frail.should they be punished for being a serial killer? the consequences will only increase suffering in the world since they can't/won't re-offend
  3a. Deterrence
    - achieves good social consequences by discouraging people from committing crime
    - how could an algorithm take this method into account?
  3b. Incapacitation
    - Achieves good social consequences by keeping criminals away from society
    - this seems to be the only method under consideration by the algorithm

Problem 3 - unfair proxies

- what if a variable that is a proxy for recidivism is something the person can't change about themselves? like race. that seems unethical - how could they change that?
- it has to be strongly correlated to recidivism but has to have new information, it can't just be a proxy for race, e.g., zip code

### Predictive Variables Instructions

Lab is done in an Excel file with Pivot tables so nothing to share here other than for step 5 you are basically just applying Problem 3 from the previous section to the COMPAS data set to see if any variables are strongly or weakly predictive and if any of them would be unethical to use as a proxy.

### Validation

not there again

### Module 03 Assessment

unavailable due to auditing

# Artificial Intelligence and Future Opportunities

## AI and Design

### AI and Future Opportunities

intro to course

### From Analytics to AI

ranking terms on x axis complexity and y axis scale

- Analytics / Business intelligence is low complexity, small scale
- Big data is slightly more complex, much bigger scale
- Data Science instead is much more complex, but slightly more scale than Anal/BI
- AI is more complex and bigger scale.

He separates AI as being predictive modelling, deep learning techniques for human-like behaviour including Computer Vision and Natural Language Comprehension. This is funny to me because that's a reductive view of AI but ok.

Whereas, he says Analytics/BI, Big Data, and Data Science are more just Analysis, Visualization, storage/processing, and basic predictive modelling (regression, classification, and clustering)

### AI Design Principles

These principles come from Microsoft's work but they want it to extend out.

1. AI must be designed to assist humanity & maximize efficiencies without destroying the dignity of people (naturally, this slide has a screen grab from Halo with Master Chief staring at a hologram of Cortana...)
  - augment humans
  - empower humans, not replace
  - enable improvement of people, gov, and society
  - industry/domain/purpose/geolocation/regulation
2. AI must be transparent, and have algorithmic accountability, so humans can undo unintended harm
  - AI should be fair, inclusive, and should not discriminate against any particular group of individuals or valid outcomes
  - bias/cleaning-extraction-learning algorithms
  - choice of target variable, class labels, and performance metric
3. AI must guard against bias
  - AI should pair _innovation_ with _trust_
  - trust that you strive to be _fair_ and benefit people
  - trust that problems will be corrected, that harm will not remain hidden
  - minimize risk of harm and distrust by being transparent
  - be able to identify/correct harmful outcomes
  - should respect context: don't read email to send us ads
  - is my performance metric biased? is this the right target, feature selection?
  - is there bias in my input/output?
4. AI must be designed for intelligent Privacy
  - Ai must _respect customer wishes_ on privacy. _Do Not Leak_. Leave people alone
  - protect personal data and identifying info
  - do not surprise with unexpected uses of data. comply with policy/regulation
  - minimize collection, use only what needed. don't contact users against wishes
  - GDPR focuses on personal data, not PII => do you know the difference?
5. AI must be secure
  - AI must ensure _Confidentiality, Integrity & Availability_ of personal data.
  - System is free of known vulns. provides controls for _protection, detection & response_ to malicious behaviour
  - different than regular security
  - I stopped writing down notes here becaues I think this comes from a presentation I can download later

### Example - Autonomous Cars

- cybersecurity issues
  - hackers to take control of a semi- or fully autonomous car
  - self-driving cars will require smart roads for operation, smart cities technology
  - DARPA funded research hacked a car a Wired driver was driving (see the magazine article)
- liability issues
  - shifting the liability between the driver and the autonomous car
  - who is responsible for the harm caused? driver? car?
  - tesla autopilot vehicle crashed and killed the driver. who is at fault? there could be negligence law, like negligent instruction (or even defective instruction) saying Tesla did not properly inform drivers they needed to pay way more attention

### Values Like Ours

1. AI will exceed human intelligence
2. Humans will eventually lose full control

How do we design the future we want, where super intelligence doesn't just wipe us out?

Value Loading (teaching lessons in values to AI)
1. Must be General, not directed to specific situations
2. Must first have a basic concern with human well-being

Ethics can only be taught to someone who already values human well-being

### Further Reading

Bostrom, Nick. Superintelligence: Paths, Dangers, Strategies. Oxford University Press; Oxford, 2014 ed.

Satya Nadella's six design principles for AI: https://www.theverge.com/2016/6/29/12057516/satya-nadella-ai-robot-laws

Information Commissioner's Office. “Big data, artificial intelligence, machine learning and data protection.” https://ico.org.uk/media/for-organisations/documents/2013559/big-data-ai-ml-and-data-protection.pdf

## XAI

### Why XAI

eXplainable AI. - "Machine learning systems that have the ability to explain their rationale, characterize their strengths and weaknesses, and convey an understanding of how they will behave in the future" (according to DARPA)

GDPR attempts to enshrine the "right to an explanation". e.g., why was I denied credit?

### XAI - The Issues

1. Tradeoff between explainability and performance
2. To whom are we expecting it to be explainable?
3. How similar exactly AI will eventually be to human intelligence? Will machines understand their own processes? Because humans aren't super reflective, and it's believed by many that humans make a decision, and then explain it later. Should machines do that too?
4. What does explainability mean? We want non-inscrutable algorithms, but in literature people have been talking about different things: transparency, justification, demonstration, interpretation.
5. Explainability: different for different types of algorithms?

These last two issues are especially difficult.

### XAI - Complex Algorithms

Some algorithms are highly explainable, or at least could be designed to be that way, but this does not seem to be true of all algorithms and is a major complication of the XAI objective.

### XAI or GAI

Explainability as transparency?
- problem: they use correlation, whereas we're more comfortable with causation (i.e, I know something for sure)

Explainability as justification?
- problem: giving the reasons in terms of the principles that could explain our true opinions. this won't help much. Deep Blue was trained on principles, but many AI don't have principles or learn them (AlphaGO)

Explainability as Interpretation?
- what kinds of concepts are nested in interpretability? Little agreement. Can humans interpret what's going on in an AI?

Governable Artificial Intelligence (GAI)
- we may never understand how algorithms come up with their conclusions. So we should govern or regulate the algorithms. Peter Norvig wrote this. He claims analyzing the output of the AI is better than understanding the system. Similar to Auditing, or Verification. Another stream of thought calls for Accountability.
- What these concepts have in common is an attempt to manage AI rather than explain how it reaches its conclusions

### Further Reading

Bornstein, Aaron. “Is Artificial Intelligence Permanently Inscrutable?” http://nautil.us/issue/40/learning/is-artificial-intelligence-permanently-inscrutable

Gunning, David. “Explainable Artificial Intelligence.” https://www.darpa.mil/program/explainable-artificial-intelligence

Weinberger, David. “Our Machines Now Have Knowledge We'll Never Understand.” https://www.wired.com/story/our-machines-now-have-knowledge-well-never-understand

## Lab

### Assignment

blah

### Algorithms and Accountability

they talk about the lab, this time I do IRAC first, not with the video

### IRAC Case Study

Given a hypothetical case, they ask you to do the IRAC method. Here's my quickie:

Issue: The algorithm is using race and gender to predict recidivism, and
Rule: Race and gender are protected classes in the constitution, and
Application: this jail is owned by the county so the protected classes apply, and therefore
Conclusion: they cannot use race and gender in the inputs.

### IRAC Suggested Answers

I got it right, but their answer has way more detail and information and is worth reading

### Predicting Recidivism without Using Protected Classes

There are _SO MANY TYPOS_ in this one.

### Validation

no access

### Module 04 Assessment

no access

# Final Evaluation

## Final Evaluation

### Module 05 Assessment

no access

## Wrap Up

### Wrap Up

Little plug for their digital dignity company

## Post-Course Survey

### Post-course Survey

meh
