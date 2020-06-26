### Product / System features
Making a good feature takes a few steps:
1. Idea  
  In order to get started you have to think of the end goal, the purpose of feature. 
2. Specification  
  It needs to be clear what the end behaviour of the feature is going to be. What happens if I click this, what data will be presented, how will the page render and so on.
2. Implementation discussion / strategy  
  It is not always possible to achieve what you want with the resources you are willing or capable of spending on the feature. Here it is the job of the programmer to let the project owner know what can and cannot be done, what the compromises may need to be, or that it is not possible at all. This step may require research to find out whether there are tools that may help achieve the goal easier.
6. Writing the specification as code  
  The expected behaviour can be expressed in words, but that is not very helpful for the programmer in question. The programmer needs be able to specify the requirement in the form of a test. This may be a full feature test that will mimic the user's (or other program's) behavior and assert that the implementation is behaving as expected, or it may be a smaller test that is asserting that a smaller piece of code, a unit, module or whatever you want to call it, behaves as the programmer wants it to when his own code interacts with it.
2. Implementing the necessary code  
  The programmer writes the implementation that fulfills the tests that he has created. In this older tests and implementation will need to be considered as well, so that it all interacts correctly.
3. Review  
  The product owner and perhaps teammates will review the feature and may have opinions on either the requirements or the implementation itself. It is sometimes not possible to know what you don't want until you see it.
5. Deployment  
  The new code is put up where users will use it.
2. Feedback  
  People have opinions. Sometimes they differ from the programmer and the product owner. This may send you back to point 1.



### Scrum vs Kanban
While both are methodologies within the same mindset, they are not mutually exclusive and one can use the principles of both in a single workflow, with perhaps a bit of redundancy.

Scrum is very tailored to software development, but could be used in order to create a physical product or process, with the drawback that it does not look forward and requires a very malleable product. Most of all it tells you who does what and in what time it is expected to be done.
It's base lies in the principle of iterative improvement of the product, in small chunks that have in implementation time that is limited to a "sprint".
Scrum could be used for prototyping a physical product.

Kanban takes a step back from the product and instead focuses on the process that creates the product. This is a better framework when the product itself is not the most important part, but rather the creation of it. What Kanban gives you is a set of tools to visualize and improve the workflow and eliminate unnecessary steps in your process.
Kanban would be used to make mass manufacturing more efficient, rather than prototyping.

During this bootcamp we have built stuff once, perhaps a few times when it comes to basic modules or scaffolds.
This has made Scrum the tool of choice and has also made it easier to collaborate due to more defined roles within the team, with task designated by team to the team.

### Continuous Integration
CI for short, has throughout this bootcamp been a wakeup clock for when you have written your brilliant feature and you are passing all your tests, but you forgot that you will need to recreate the database, or add an environment variable or that sometimes, tests do not pass for everyone, because you forgot that not all browsers are created equal.
We have been using semaphore during the bootcamp, and it has most of the time been quite a hassle free experience.
At this final project it did however become apparent that browsers are not the same, even if both are Chrome. At these times we have sometimes cursed the CI, but also cherished it, as we know that taking all factors into account will allow us to build a better product.


### Automated tests  
The automated testing grows on you, more and more, as the application grows in its repo.
Having a full suite of end to end testing is a great relief to have when you are almost done and you need to make sure you did not break anything. Using RSpec request tests allows you to simulate a request, and check what your application would respond with. Sometimes you just have to change what was there before you. If the person before you did their job, however, they made sure that you cannot mess their code up, without being told by the tests.
Cypress will let you do this for your javascript clients. You can make it pretend a user is clicking about, and make assertions about what the page is displaying. This good for capturing the top level behaviour of your application, but may fail to tell you exactly what the underlying issue is.
Unit testing breaks down your application to digestable chunks. You can take a function, and see what it does, or take a single page on your site, and see if the button actually sends of the request you want when it is clicked.
You can also take a single object/class/model and see that an instance of it behaves the way you want. Perhaps it should validate that an attribute of it has a certain type or fail otherwise, or it should have a method that manipulates it in some way and you want to test that it actually happens.

In my own experience it is very difficult to predict exactly what a user will do. expect(the_worst).to have_been_called.