<img src="https://i.imgur.com/go18uJE.jpg">

# Star Wars API - React AJAX practice

---

## Intro

In this deliverable, you'll consume the [Star Wars API](https://swapi.dev/) and render it's data.

## Set Up

To get set up:

- Use `create-react-app` to create a React app named `react-star-wars`
- `cd` into `react-star-wars` and open VS Code.
- Open a terminal in VS Code.
- Start the React Dev Server.

## Exercises

> Styling is secondary to completing the functionality

1. Obtain all of the starships from the API and render in `<App>` a clickable `<Link>` (imported from `react-router-dom`) for each starship. The link should be styled to look like a button and contain the text of the starship's name.  For example:

	<img src="https://i.imgur.com/VERV0nk.png">

2. When a starship `<Link>` is clicked a `<StarshipPage>` component should be rendered that displays the starship's `name`, `model` and a "Return to Starship List" `<Link>` that routes back to the root route that renders `<App>`. For example:

	<img src="https://i.imgur.com/IjRwsHk.png">

5. Because the data is being loaded asynchronously, there are times, such as if the user refreshes the page while viewing the `<StarshipPage>`, that the data won't be available to render, in this case, display a "Loading..." message instead.

## Hints

- Hold the starships in state.

- The challenge is to be able to have the `<StarshipPage>` component obtain the specific starship object it needs to render. Here are a few of approaches:

	1. A nice approach is to use a slightly more complex syntax that React Router's `<Link>` offers.  This approach relies on assigning an object instead of a string to its `to` prop.  That object passed can have a `state` property that allows information to be passed to the new route. For example:
	
		```js
		this.state.starships.map(starship =>
		  <Link
		    to={{
		      pathname: '/starship',
		      state: starship
		    }}
		    key={starship.name}
		  >
		    {{starship.name}}
		  </Link>
		```
		You'll then be able to access the passed state on the route's `location` object...
		
		```js
			this.props.location.state.starship
		```
		Be sure the `<Route>` component that is rendering `<StarshipPage>` passes the `location` object to it.

	2. Another approach would be to pass to `<StarshipPage>` a method as a prop that it can call, supplying an argument identifying which starship object it wants. That argument's value could come from a URL parameter in the link that was clicked...

		Review the Client-side Routing in React lesson's _Defining Routes with URL Parameters_ section for assistance with how to define routes with parameters used to pass information to components.


## Bonus

- Enhance the `<StarshipPage>` component to render a `<PilotList>` component that lists the names of the pilots for that starship.

- If the starship has no pilots, display a "No Pilots" message.

	Hint: This requires a call to the API for each of the endpoints listed in the starship's `pilots` array. Using `async`/`await` can help with this - [here's a repl](https://repl.it/@jim_clark/Multiple-AJAX-Calls) that shows how to fetch the pilots in parallel.

---

Adapted from [SEI-DT-71 lab](https://git.generalassemb.ly/SEI/dt-71/blob/master/units/4_mern_stack/w11/d3/03-react-ajax-lab/react-ajax-lab.md)



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
===============================================================================================================
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>


This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
