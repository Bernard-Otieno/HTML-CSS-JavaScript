# What is NPM? 
Node Packet Manager, is a software packet manager and installer. It is also the default runtime package manager of Node.JS

# What is SPA? 
Single Page Application, Presents one page at a time by dynamically re-writing the webpage.

# What is the event loop?
A concept known to periodically check for pending events and execute callback functions, ensuring I/O operations do not block execution of other code.  

# What is the difference between export x and export default x? How do you import them differently?
We use 'export' to export named exports and when importing you must use the same exact name that was used during the export. For example: 

    export const number = 10;
    
    import {x,y} from './Module.js'; 

We use 'export default' to export a single default export which can be imported and given any name when imported. Simply, it is the default export from that module.

    const number = 10;
    export number;
    
    import myNumber from './Module.js';

# Why do you use className as a property in React and not class?
Class is a JavaScript keyword therefore can not be used in its original purpose from html. ClassName is used to avoid clashes

# Why should you not write the following? What will happen?
    <button onClick={setCounter(counter + 1)}> +1 </button>
We would be invoking the set counter before the the 'click' action is made rather than actually waiting for the 'click' action.

# What is object deconstruction and how is it connected to React components (example)?
A feature allowing you to rextract properties from an object and assign them to variables in a concise and readable manner. This helps with objects such as props and state objects.

      const App = () => {
      //create a user
    const user = {
      name: 'John Doe',
      age: 25,
      email: 'john@example.com',
    };
    return (
    <div>
      <h1>User Information</h1>
      <UserInfo name={user.name} age={user.age} email={user.email} />
      <UserInfoDestructured {...user} />
    </div>
    );
    };
    const UserInfoDestructured = ({ name, age, email }) => {
    return (
      <div>
        <h2>{name}</h2>
        <p>Age: {age}</p>
        <p>Email: {email}</p>
      </div>
    );
  };

    export default App;

      



# How is it possible to use HTML and JavaScript in the same function (like in a React Component)? What makes it possible under the hood?
JSX, a syntax extension that allows us to write HTML-like code in JavaScripts files. Transpilation converts JSX into JS that browsers can interprate. Babel converts JSX into JS that the browser can interprate.

# What is async/await? Bring an example
A feature in JavaScript that is used to work with asynchronous functions. 'async' is used to declare an asynchronous function while await is used to pause a function until the promise is fulfilled/rejected.

### Function that returns a Promise (e.g., fetching data)
    function fetchData() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve("Data fetched successfully!");
        }, 2000);
      });
    }
    
    async function fetchDataExample() {
      try {
        console.log("Fetching data...");
        const result = await fetchData();
        console.log(result);
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    }
    
    // Calling the async function
    fetchDataExample();



# What is a Promise? Bring an example
An object that represents failure or success of an asynchronous operation and the returned value.
## Examples of a Promise

      const newPromise = new Promise((resolve, reject) => {
        const success = true;
      
        if (success) {
          resolve("Successful!");
        } else {
          reject("Failed!");
        }
      });
      newPromise
        .then((result) => {
          console.log(result);
        })
        .catch((error) => {
          console.error(error);
        });
