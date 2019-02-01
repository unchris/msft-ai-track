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

### Data Privacy and Security Best Practices

### GDPR

### GDPR, Big Data, and AI

### Further Reading

# Artificial Intelligence and Future Opportunities

# Final Evaluation
