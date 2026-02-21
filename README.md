# scientific-expert-design-resources

I created this as a resource to hold my thoughts, observations and experiences with focusing on capturing domain expert into a machine rather than think about programming specific ideas or patterns. I believe that premature abstraction and optimizations are the greatest evils in programming and are a waste of time. In contrast to over-engineering with premature abstraction, capturing your domain or system expert to represent accurately in code and thinking of experiments and tests that validate your code/programs are never a waste of time.

# Systematic Program Design

In the book "How to Design Programs", available online https://htdp.org/2025-12-27/Book/part_preface.html#(part._sec~3asystematic-design), we have a very simple and powerful approach to designing functions and programs called design recipes. This is a good approach to start coding with if you do not understand the domain well but you are in position to code and validate behavior of a program. Having something to work with in terms of code you can then break it down to experts/domains for clarity which sometimes comes later in the development process.

# Data Oriented Programming

The book "Data Oriented Programming" is an excellent resource for visualizing how data/mental models can relate to each other and it a great place to start when figuring out domains

# Functional programming structure

I've identified that a good way to represent domains is to categorize things within a domain as `DomainModels`, `DomainRules`, `PureCalculations`, `ImpureCalculations`, and `InternalFunctions`.  Using that structure, I've been finding that I can basically represent any world or domain that I've come across in existence so far whether they be real or imaginary.

# Visualization

I think a good place to start is to imagine that you intend to write a library for a specific purpose or domain. You want to first identify a DomainModel in there and establish a DomainRule. Put yourself in the shoes of a domain expert. We want to be able to encapsulate a domain expert into machine code. To be able to give a machine clear instructions, an expert would start to imagine how to give a little child with infinite pen and paper and lives in a box and can only communicate through streams of letters and numbers how to think about the domain (Church-Turing thesis). When trying to explain to a child a domain, an expert will naturally mentally think about mental domain models and rules of the domain. Code can interface with systems that don't behave the same way all the time, the act of interfacing can be called "ImpureActions." Code that is made to calculate a value or determine a decision can be called "PureCalculations." ImpureActions and PureCalculations should use DomainModels and DomainRules in way that benefits the intended user. "Program" or "Library" would be where the intended user abstractions or go to starting point would be. It takes all the pieces of the domain "rules", "calculations", "actions" and presents it to a user as intended. A person should be able to read domain models and rules and be able to figure out the domain. A person should be able to read ImpureActions and PureCalculations code and associated tests to understand how it is intended for a user to use the domain. A person sohould be able to read the Program or Library code and understand how to properly call the domain as a tool.

Unit tests would most likely be written for PureCalculations with the mindset of "how would I verify that a domain expert is encapsulated in this code?" Integration or end to end tests would be more useful to verify ImpureActions working and behaving as expected.

**edit: I've updated `Rules` concept into `Concerns` concept so that it can be more flexible and scalable and labelled better. (Think <XYZ-concerns> instead of <XYZ-rules-of-thumb>)

- `Domain Data Models`: What data does an expert need to be able to think about their problem?
- `Concerns`: What are things an expert is concerned about when they are thinking about their problem?
- `Calculations`: What does an expert have to make a calculated decision about to be useful to someone asking them a question?
- `Action`: What kind of interaction dependent task do we need an expert to take part in?

# Problem solving tiers

When you have a problem statement such as "how can I build a sophisticated spam bot that's as good as a human?" You want to be able to predictably break it down into workable tasks that people can work on. These series of transformational breaking down of a problem I find very useful and incremental and it goes as such.

**Problem -> Compututational Theory components -> Architectural Design with Event Modelling -> Scientific Domain Expert Code Implementation**

These series of thinking in my experience leads to all the important questions being asked and results in really good end product.

An example template that I did can be found here https://github.com/FullstackGJJ/employee-specialty-decoder/tree/main/Haskell where you can see how the `Description.md` housed within a directory to encapsulate a domain is done. I plan to do more in the future in other languages for more examples.

When working with a problem, you can start out by imagining an ideal finalized automated solution. From there, you want to work backwards and take away responsibility that is delegated to the user instead of the solution. As you strip away responsibilities from the solution, you have a roadmap for how you can start from nothing to a complete solution. During building the solution, you want to model out values and data that are computable and build assuming they exist, then make them exist and extract out the domain or start from domain that is responsible for values/data existing.

When developing a domain, you don't necessarily have to only start with breaking down the domain. If you feel stuck or you feel like you have to interact with a machine, feel free to just have sample data to use and start coding to perform actions that a domain expert would want. The most importanat part is that eventually domain expert level thinking that is computable is broken down in a way that can be explained to a child with the associated mental models, rules of thumb, decision making, and actions (because instructions are clearer when you imagine a machine as a child).

A good workflow in Scheme is to have the mental models of a domain laid out. Then sample data can be used and you can incrementally create methods and functions that manipulate the data to where it needs to go using the REPL and store it as code. You can grab the process and functions and break down if they belong to other domains, rules of thumbs, calculations and actions
