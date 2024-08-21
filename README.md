# REACT FORMS

What are forms?<br>
Forms are a collection of inputs data that eventually submitted either to authenticate user
a or collect data and save it on the database e.t.c.

## Important aspects about forms
1. The onSubmit handler should be set on the entire form:
    ```javascript
        <form onSubmit={handleSubmit}>
            //    labels & inputs
        </form>
    ```
   This allows centralized control of the form behavior.<br>
   Avoid on submit on buttons like.<br>
2. The default behavior must be prevented via onSubmit handler function to allow custom logic before form submission.
   ```javascript
    function handleSubmit(event){
        event.preventDefault()
   }
    ```
    Note: **On submission forms tend to be sent to certain urls or page specified on the action 'attribute' of the form causing the**
         **page to refresh/reload. This is undesired in react and that's why it is prevented. Remember react apps are SPAs.**

## Collecting data from forms during submission
When the default behavior is prevented.
The data on the forms can be collected in with any of the methods below.

1. Use state to store inputs data which are updated on every keystroke via **two-way bidding**.
2. Use refs to collect the data from the inputs by accessing the DOM directly. This is not recommended as it bad practice to manipulate DOM directly.
3. Use the form data object provided by the browser.

## Resetting forms
Depending on the data collection approach used.
Here is how to reset forms;

1. Set states to empty strings
   e.g.
   ```javascript
        setEnteredValues(""); //resetting a form in state
    ```
2. Update refs with empty.
   e.g.
   ```javascript
        email.current.value = ""; // reseting the email input in useRef
    ```
3. Reset the form data object
    e.g.
   ```javascript
        event.target.reset(); // resetting in FormData Object
    ```

