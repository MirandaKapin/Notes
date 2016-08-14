# JSX - React Notes

## Lifecycle Methods




### `componentWillMount`
[Source](https://facebook.github.io/react/docs/component-specs.html#mounting-componentwillmount)
> Invoked once, both on the client and server, immediately before the initial rendering occurs. If you call `setState` within this method, `render()` will see the updated state and will be executed only once despite the state change.

#### Example
```javascript
var Something = React.createClass({
	componentWillMount: function () {
		...code here...
	}
});
```

#### Notes
* `componentWillMount` is automatically fired by React as the component is added to the DOM
	* Will be fired immediately **BEFORE** the component is rendered to the screen
* No Access to `refs` or DOM




### `componentDidMount`
[Source](https://facebook.github.io/react/docs/component-specs.html#mounting-componentdidmount)
> Invoked once, only on the client (not on the server), immediately after the initial rendering occurs. At this point in the lifecycle, you can access any refs to your children (e.g., to access the underlying DOM representation). The `componentDidMount()` method of child components is invoked before that of parent components.
> 
> If you want to integrate with other JavaScript frameworks, set timers using `setTimeout` or `setInterval`, or send AJAX requests, perform those operations in this method.

#### Example
```javascript
var Something = React.createClass({
	componentDidMount: function () {
		...code here...
	}
});
```

#### Notes
* `componentDidMount` is automatically fired by React **AFTER** the component is added to the DOM




### `compontentWillReceiveProps`
[Source](https://facebook.github.io/react/docs/component-specs.html#updating-componentwillreceiveprops)
> Invoked when a component is receiving new props. This method is not called for the initial render.
> 
> Use this as an opportunity to react to a prop transition before `render()` is called by updating the state using `this.setState()`. The old props can be accessed via `this.props`. Calling `this.setState()` within this function will not trigger an additional render.
---
> **Note:**
> One common mistake is for code executed during this lifecycle method to assume that props have changed. To understand why this is invalid, read [A implies B does not imply B implies A](https://facebook.github.io/react/blog/2016/01/08/A-implies-B-does-not-imply-B-implies-A.html)
> 
> There is no analogous method `componentWillReceiveState`. An incoming prop transition may cause a state change, but the opposite is not true. If you need to perform operations in response to a state change, use componentWillUpdate.

#### Example
```javascript
var Something = React.createClass({
	componentWillReceiveProps: function (nextProps) {
		...code here...
	}
});
```
 


### `componentDidUpdate`
[Source](https://facebook.github.io/react/docs/component-specs.html#updating-componentdidupdate)
> Invoked immediately after the component's updates are flushed to the DOM. This method is not called for the initial render.
> 
> Use this as an opportunity to operate on the DOM when the component has been updated.

#### Example
```javascript
var Something = React.createClass({
	componentDidUpdate: function (prevProps, prevState) {
		...code here...
	}
});
```

#### Notes
* Fired immediately following an update to the application
	* i.e. to the props or the state




### `componentWillUpdate`
[Source](https://facebook.github.io/react/docs/component-specs.html#updating-componentwillupdate)
> Invoked immediately before rendering when new props or state are being received. This method is not called for the initial render.
> 
> Use this as an opportunity to perform preparation before an update occurs.

#### Example
```javascript
var Something = React.createClass({
	componentWillUpdate: function (nextProps, nextState) {
		...code here...
	}
});
```

#### Notes
* Gives the ability to do a function on the next props and next state




### `componentWillUnmount`
[Source](https://facebook.github.io/react/docs/component-specs.html#unmounting-componentwillunmount)
> Invoked immediately before a component is unmounted from the DOM.
> 
> Perform any necessary cleanup in this method, such as invalidating timers or cleaning up any DOM elements that were created in componentDidMount.

#### Example
```javascript
var Something = React.createClass({
	componentWillUnmount: function () {
		...some code example here...
		clearInterval(this.timer);
		this.timer = underfined;
		...end example...
	}
});
```
#### Example Uses
* In a timer application, clear the timer interval see code example above

#### Notes
* `componentWillUnmount` is automatically fired by React right before the component is removed from the DOM

