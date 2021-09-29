# AmirthavarshiniSockalingamBama-Book

**Chapter 15** This is the final chapter and it deals with deploying the application in heroku. We separate two repositories into api and ui since package.json should be in the root directory and I have also created new google client id for both the urls of api and ui. We have to set cookie domain in a correct way or we wont be able to add / delete issues - unaunthenticated user error would show up. These are some of the issues I faced. 

https://tracker-ui-amirthavarshini.herokuapp.com -  ui deployment link
--
https://tracker-api-amirthavarshini.herokuapp.com/graphql - api deployment link 


 ![ch15](/readme_images/ch15.png)

---




**Chapter 14** Most applications need to identify and authenticate users. It deals with integrating with one of the social sign-ins.
We need a console project and a client ID to identify the application.Just authenticating with Google is not enough; we’ll need to do something with the authentication. Validating a token at the back-end is required as a measure of security. That’s because the back-end cannot trust the UI to have done the authentication, as it is public and can also respond to any HTTP request, not just from the Issue Tracker UI.Although we verified the token and used the name from the back-end, we did not persist the information. This means that on a browser refresh, the information about the sign-in would disappear, forcing the user to log in again.One way to persist the authentication information is by creating a session on the back-end, identified by a cookie.JSON Web Tokens (JWT) solve this problem by encoding all the session information that needs to be stored in a token. Then authorization part is dealt with. React context, cors with credentials and cookie domain are other later topics covered. 

 ![ch14](/readme_images/ch14.png)


![ch14output](/readme_images/ch14output.png)


---



**Chapter 13** deals with Advanced Features. -refactor the UI code to reuse common code across many components that display the Toast messages. MongoDB provides in terms of getting summary data of a collection, that is, aggregates.In issue counts api changing tp have one element per owner rather than one element for each owner-status combination, and one property each for the count of each status.Using cross tab or pivot table for reports. Changing list api to support pagination. Pagination UI i-React-Bootstrap has support for the pagination presentation. Undo delete API -implement the API required for this, one that restores a deleted issue, then creating delete UI to support this. Text Index API -an autocomplete that finds all issues matching the words typed. Instead of implementing the search component ourselves,  using one of the popular controls available, choosing React Select.

 ![ch13](/readme_images/ch13.png)

---
**Chapter 12** deals with server rendering. The ability to generate HTML on the server in addition to being able to render directly to the DOM.Splitting the current source code into three directories, one for each set of files. We used the ReactDOM.render() method to render a React element into the DOM. The counterpart method that is to be used to create an HTML on the server side is ReactDOMServer.renderToString()Although the method itself is a simple one, the changes that we need to make in order to use it are not. Next is webpack for the server. The first thing we’ll do is add a new section in the webpack.config.js file for the server configuration. Webpack allows an array of configurations to be exported.HMR.on a restart, the HMR middleware is reinstalled, but the browser tries to connect to the original HMR, which is no longer there.The solution to all this is to automatically reload the modules even in the back-end using HMR. Next topic server router- On the server, React Router recommends that we use a StaticRouter in place of a BrowserRouter. Also, whereas the BrowserRouter looks at the browser’s URL, the StaticRouter has to be supplied the URL. Based on this, the router will choose an appropriate component to render.
Data from API is a topic because the string should come from the API server.Data fetcher is the next main topic in this chapter. Redirects -a request to the home page, that is, /, returns an HTML from the server that contains an empty page. It seems to work because after rendering on the browser, React Router does a redirect to /issues in the browser history.

 ![ch12](/readme_images/ch12.png)

---


**Chapter 11** deals with bootstrap. Buttons, panels and tables are included in the first few sections by including bootstrap code. Next is forms. Forms can be styled and laid out in a variety of ways using Bootstrap. Grid system - The default way the form gets laid out in the Issue Filter is not great, as it occupies a lot of space vertically, and the input controls are unnecessarily wide. But this may work well for narrow screens or narrow sections within a page. When we want the form controls next to each other, including the labels, we use inline forms. The next type of form we will explore is the horizontal form, where the label appears to the left of the input, but each field appears one below the other. Apart from it we also learn about validation alerts. Toas are used to informational alerts. Modals - When a modal is rendered, it is rendered outside the main <div> of the DOM that holds the page.
 ![ch11](/readme_images/ch11.png)

 ---










**Chapter 10** deals with user inputs.Converting the hard-coded filter to something more flexible with user input, and then we’ll fill in the Edit page with a form.To be able to show a value in the input, it has to be controlled by the parent via a state variable or props variable. This is done simply by setting the value of the input to that state or props variable. Thus, the input will directly reflect that value, and the React component that renders the form will also control what happens in that form on subsequent user input.Next is filters.
 A useful filter in the real application would be one on the Assignee field. Editing form is next topic. We will need to store the current value of each input, which correspond to the fields of the issue being edited. Later to this, different inputs are handled and also updating different fields is introduced. 
 ![ch10_1](/readme_images/ch10_1.png)
 ![ch10_2](/readme_images/ch10_2.png)

---








**Chapter 9** deals with routing. Even in a single-page application (SPA), there are in fact multiple logical pages (or views) within the application. It’s just that the page load happens only the first time from the server. After that, each of the other views is displayed by manipulating or changing the DOM rather than fetching the entire page from the server.Te URL’s path and the route’s path need not be a perfect match. Whatever follows the matched part in the URL is the dynamic part of the path, and it can be accessed as a variable in the routed component.React Router provides a better and more convenient way to create links via the Link component. This component is very much like an href, but the paths in a Link are always absolute; it does not support relative paths and much more differences.The later part involves programming navigation.Then adding a description via nesed routes. The next other thing is browser history router ,for a browser request, the page would have been constructed on the browser. We’ll not be generating the page to be displayed.

![ch9](/readme_images/ch9.png)


---

**Chapter 8** introduces Modularization and Webpack. Generally it means splitting into multiples files to improve the code efficiency.
Initally we first start with Back-end modules with require and exports.The require() element is a function that can be used to import symbols from another module. The parameter passed to require() is the ID of the module.The variable module.exports to be set to the function, so that it can be used after importing the file. Similarly Front-end modules and webpack is introduced.Using webpack, dependencies can be defined using statements equivalent to require() that we used in Node.js. The tools then automatically determines not just the application’s own dependent modules, third-party library dependencies too.Webpack is capable of combining these two steps, without the use of intermediate files which is possible using loaders. Later to that , we have used webpack to include libraries which spans from cdns and further more. Hot Module replacement changes modules in the browser while the application is running, removing the need for a refresh altogether. Finally debugging is discussed. Webpack solves the problem of debugging by giving source maps, things that contain out original source code.
 The below are the two images which fetches from both local host 3000 and 8000 and also shows HMR connected. But since I wasnt able 
 to display everything in a single output. I have displayed two outputs.(after confirming with TA). 

 The issues I faced were few things when I ran npm run lint to check code correctness , which I solved it. 

![ch08output1](/readme_images/ch8_output1.png)
![ch08output2](/readme_images/ch8_output2.png)


---

**Chapter 7** introduces Architecture and ESlint. It separates into two serves ui which renders the front end and api server which is backend. There would be three deployment environments: development, staging, and production.The server ports and MongoDB URL for each of these would be quite different. Later to this, proxy based architecture is introduced. Browsers prevent malicious intervention by requiring that such requests be explicitly permitted. The kind of requests that can be permitted is controlled by the Same-origin policy as well as parameters controlled by the server, which determines if the request can be allowed. This mechanism is called cross-origin resource sharing or CORS for short. Now after this linter is introduced.A linter checks for suspicious code that could be bugs. It can also check whether your code adheres to conventions and standards that you want to follow across your team to make the code predictably readable.

![ch07api](/readme_images/ch7_api.png)
![ch07ui](/readme_images/ch7_ui.png)



---






**Chapter 6** deals with MongoDb basics. It gives a introduction on collections. After installing , it touch bases on different commands involving mongodb crud operations. It details about projection, update and delete. Later to that, it merges mongodb with the issuetracker application, it takes the input from the database rather than from the issue array we earlier had. It improves the call back paradigm to async-wait paradigm. Then indexes are introduced and talked about. Reading and writing to MongoDb are discussed. 

![ch06](/readme_images/ch6.png)









---

**Chapter 5**  deals with fetching and storing the data using APIs from the Express and Node.js server in addition to the static HTML file. This will replace the hard-coded array of issues in the browser’s memory. REST APIs were resource based, whereas GraphQL is graph based. Graphql schema file is first introduced, reason being when the schema grows bigger, it would be useful to separate the schema into a file of its own.Then list api is considered, started by modifying the schema to define a custom type called Issue. Then its integrated into UI section.To use the APIs, Ajax calls are called. We have used libraries since  including the entire jQuery library would be waste. Sorting and filtering on dates is difficult so then we have made dates as  JavaScript’s native Date objects. Later to this , we have done an API for creating a new issue in the server, followed by API integration. GraphQL has a way to factor dynamic values out of the query and pass them as a separate dictionary called variables. Query variables is discussed. Followed by this input validations and displaying errors is done. 

I faced many issues because of typos , few were very hard to figure out. The TA's were kind enough to help and spot them. 

![ch05](/readme_images/ch5.png)



---







**Chapter 4** explains the React State , it explains how the  state of a component is captured in a variable called this.state in the component’s class. Then it gives a introduction of Async state initialization. The main gist it tells through that is the state can only be assigned a value in the constructor. After that, the state can be modified, but only by a call to React.Component’s this.setState() method. Further to that it explains react's life cycle methods which are ComponentDidMount(),ComponentDidUpdate(), ComponentWillUnMount()and shouldComponentUpdate().Then Updating a state is brought in and it is explained by adding a method in IssueTable to add a new issue. Lifting a state up is nothing tedious , it is just moving the initiation of the creation to where it belongs. We are doing this by having the common parent contain the state and all the methods that deal with this state.By lifting the state up on level to IssueList, information can be propagated down to IssueAdd as well as to IssueTable. Because interation among siblings is hard , almost impossible. Even handling is the next topic of the chapter,
in this we learn how to add an issue on the click of a button.The last topic of this chapter is stateless components. The aim of this is IssueRow and IssueTable have nothing but a render() method. So to improve the efficiency, it is recommended that such components are written as functions rather than classes. 

Issues faced is one error when I wrote issues , and the output wasnt rendered , then I inspected and found the error that there is nothing found as issue, because
I have declared it as issues in the function. Then I noticed and changed it back to issue. 

![ch04](/readme_images/ch4.png)





---
**Chapter 3** explains React components can be composed using other components and basic HTML elements. We learned it by building a Issue Tracker application. 
Firstly we created React class to create real components, then these can be reused within other components. React classes are created by extending React.Component, the base class from which all custom classes must be derived. Next we proceed to create user defined components. Then by running npm run watch in a console and  start the server using npm start in a separate console. Therefore, any changes to App.jsx should have been automatically compiled. A component takes inputs and its output will be the UI of the component. For now we have composed components without variables, next we will proceed to creating with variables. This is made possible by passing different input data from a parent component to a child component and render it variedly in different instances. This is one method, the next method will be passing
data using the contents of the HTML- like node of the component. We can access it from the child component by using this.props.children. The next topic is Dynamic Composition. We replace hardcoded data by dynamically generated set of components from an array of issues.

Havent faced any issues when doing this. 

![ch02](/readme_images/ch3.png)















---
**Chapter 2** gives a basic introduction on how we should use the Mern components. It also explains us with all the installations needed to get started. 
It first explains serverless hello world , this is done with the help of react.create element calls. After to this to avoid complication, we use jsx transform which
is similar to html. To convert JSX to pure javascript we use a compiler called Babel. Later to this express is introduced. 
An Express application is web server that listens on a specific IP address and port. After we start the server, we should see a message saying the application has started on port 3000. 
and when we open the browser and type http://localhost:3000/index.html in the URL bar , we will get the output. After this, it introduced us how to move 
the transformation of JSX to JavaScript to the build stage, because until now this transformation was happening during run time. Later to this , it also gave us the 
steps on how to make old browsers support certain new functions. Finally it gave a walk through with automation which is 
when there are many command line parameters for the command , it will be difficult to type on the shell so in that case these custom commands can
be specified in the scripts section of package.json.

The issues that I ran into while doing this chapter was only with the installation of nvm, I installed it more than once, because somehow my mac terminal wasnt picking 
up nvm command, it was showing command not found ,then I followed whatever mentioned in the canvas to trouble shoot. To be precise I did this - "
If you use bash, the previous default shell, your system may not have a .bash_profile file where the command is set up.
Create one with touch ~/.bash_profile and run the install script again. Then, run source ~/.bash_profile to pick up the nvm command."

![ch02](/readme_images/ch2.png)
