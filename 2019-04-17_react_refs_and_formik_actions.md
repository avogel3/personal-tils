# Using React Refs to Access Formik Actions

##### 04/17/2019


Say you need to access the Formik actions (passed to handleSubmit) outside of the submit function, you can get access to them by using a React.Ref.

Create the `ref` in the constructor

```javascript
constructor(props) {
  super(props)
  this.formik = React.createRef()
}

```

Now, we will put it together with a button to reset our form.

```javascript
import React from 'react'
import { Formik } from 'formik'
import { Button } from 'react-native'

class LoginForm extends React.Component {
  constructor(props) {
    super(props)
    this.formik = React.createRef()
  }
  handleSubmit = (values, actions) => {
    // Some submit logic...
  }
  resetForm = () => {
    if(this.formik.current) this.formik.current.resetForm()
  }
  render() {
    return(
      <Formik 
        ref={this.formik}
      	initialValues={{ email: '', password: ''}}
	onSubmit={this.handleSubmit}
      >
        {props => (
  	  // Form stuff
        )}
      	<Button onPress={this.resetForm} title="Reset Form" />
      </Formik>
    )
  }
}

export default LoginForm

```


Tags: React, React Native, Formik, Refs
