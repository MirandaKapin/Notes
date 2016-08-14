# JSX - React Notes

## React Specific Functions

### Lifecycle Methods

#### componentWillMount
[Source](https://facebook.github.io/react/docs/component-specs.html#mounting-componentwillmount)
> Invoked once, both on the client and server, immediately before the initial rendering occurs. If you call `setState` within this method, `render()` will see the updated state and will be executed only once despite the state change.

##### Example
```javascript
var Something = React.createClass({
	componentWillMount: function () {
		...code here...
	}
});
```

#### componentDidMount
[Source](https://facebook.github.io/react/docs/component-specs.html#mounting-componentdidmount)
> Invoked once, only on the client (not on the server), immediately after the initial rendering occurs. At this point in the lifecycle, you can access any refs to your children (e.g., to access the underlying DOM representation). The `componentDidMount()` method of child components is invoked before that of parent components.
> If you want to integrate with other JavaScript frameworks, set timers using `setTimeout` or `setInterval`, or send AJAX requests, perform those operations in this method.

##### Example
```javascript
var Something = React.createClass({
	componentDidMount: function () {
		...code here...
	}
});
```

#### componentDidUpdate
[Source](https://facebook.github.io/react/docs/component-specs.html#updating-componentdidupdate)
> Invoked immediately after the component's updates are flushed to the DOM. This method is not called for the initial render.
> Use this as an opportunity to operate on the DOM when the component has been updated.

##### Example
```javascript
var Something = React.createClass({
	componentDidUpdate: function () {
		...code here...
	}
});
```

#### componentWillUnmount
[Source](https://facebook.github.io/react/docs/component-specs.html#unmounting-componentwillunmount)
> Invoked immediately before a component is unmounted from the DOM.
> Perform any necessary cleanup in this method, such as invalidating timers or cleaning up any DOM elements that were created in componentDidMount.

##### Example
```javascript
var Something = React.createClass({
	componentWillUnmount: function () {
		...code here...
	}
});
```