# Project Description

The project converts an existing project the [burger-builder](https://github.com/stLoiz/react-project-burger-builder) with class based components to functional components and uses hooks.<br/>
You can checkout the project [here](https://www.stellaloizou.eu/burger-builder-react-project/)<br/>
The main goal is to display how you can use hooks and modern features of React:

- Functional components instead of class based components<br/>
- Hooks like:
  - useState()
  - useEffect()
  - useCallBack()
- React/Redux Hooks:

  - useDispatch()
  - useSelector()

- The best practices for optimization in React:
  - React.lazy
  - React.memo

### What are the main functionalities of this project?

The user can:

- sign in/up
- build a burger by adding or removing ingredients
- order the burger by fill in a form
- see his orders

## To run the project

1. Clone the project

2. In the project directory:

- run `npm install`

3. Create the database

I used [firebase](https://firebase.google.com/?gclid=EAIaIQobChMIpNfBiZqd6QIVlO7tCh3_xQDlEAAYASAAEgImxfD_BwE) to create a dummy database. You can do the same as it is really quick:

- Click on this [link](https://firebase.google.com/?gclid=EAIaIQobChMIpNfBiZqd6QIVlO7tCh3_xQDlEAAYASAAEgImxfD_BwE) and create a project.

- Go to the Database tab of the newly created project and choose Realtime Database/Create database

- Add a table by clicking on the `+` sign:

  - `Name`: ingredients
    - `Name`: salad `Value`: 0
    - `Name`: meat `Value`: 0
    - `Name`: bacon `Value`: 0
    - `Name`: cheese `Value`: 0

- Configure the database rules under the database tab by adding the following json:

        `{
         "rules": {
             "ingredients": {
                 ".read": "true",
                 ".write": "true",
              },
             "orders": {
                 ".read": "auth != null",
                 ".write": "auth != null",
                   ".indexOn": ["userId"]
             }
         }
       }`

- Enable Authentication in database:
  - Go to Authentication tab
  - Click on Set-up sign-in method
  - Enable Email/Password

4. Conifigure **env.**

Create a file .env to the root of the project directory and add this:

`REACT_APP_FIREBASE_URL='your/firebase/url'`
`REACT_APP_FIREBASE_SIGN_UP_URL='https://identitytoolkit.googleapis.com/v1/accounts:signUp?key=yourKey'`
`REACT_APP_FIREBASE_SIGN_IN_URL='https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key=yourKey'`

To get your FIREBASE URL go to the firebase project that you created, it is under the database tab.
To get the key Click on Settings of the project and under general tab you will see the Web Api Key

5. In your project directory run `yarn start`

## Testing

Some test are added just to show how jest and enzyme testing works:

To run the tests `yarn test`
