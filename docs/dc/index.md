# ML Bytes

- Dynamic Components

    - [Data Manager](data-manager/index.md)
	- [Application Protector](application-protector/index.md)
	- [Binding Recordset](binding-recordset/index.md)
	- [Dynamic Report](dynamic-report/index.md)
	- [Image Button](image-button/index.md)
	- [Form Flipper](form-flipper/index.md)
	- [Form Translator](form-translator/index.md)
	- [Help Authority](help-authority/index.md)
	- [Data Entry Validator](data-entry-validator/index.md)
	- [Returnkey- Enabled](returnkey-enabled/index.md)
	- [Num2Text](num2text/index.md)
	

<!-- modify this form HTML and place wherever you want your form -->
  <form id="fs-frm" name="simple-contact-form" accept-charset="utf-8" action="https://formspree.io/f/mnqlleyl" method="post">
  <fieldset id="fs-frm-inputs">
    <label for="full-name">Full Name</label>
    <input type="text" name="name" id="full-name" placeholder="First and Last" required="">
    <label for="email-address">Email Address</label>
    <input type="email" name="_replyto" id="email-address" placeholder="email@domain.tld" required="">
    <label for="message">Message</label>
    <textarea rows="5" name="message" id="message" placeholder="Aenean lacinia bibendum nulla sed consectetur. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Donec ullamcorper nulla non metus auctor fringilla nullam quis risus." required=""></textarea>
    <input type="hidden" name="_subject" id="email-subject" value="Contact Form Submission">
  </fieldset>
  <input type="submit" value="Submit">
</form>



<style>
body {font-family: Arial, Helvetica, sans-serif;}
* {box-sizing: border-box;}

.form-inline {  
  display: flex;
  flex-flow: row wrap;
  align-items: center;
}

.form-inline label {
  margin: 5px 10px 5px 0;
}

.form-inline input {
  vertical-align: middle;
  margin: 5px 10px 5px 0;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #ddd;
}

.form-inline button {
  padding: 10px 20px;
  background-color: dodgerblue;
  border: 1px solid #ddd;
  color: white;
  cursor: pointer;
}

.form-inline button:hover {
  background-color: royalblue;
}

@media (max-width: 800px) {
  .form-inline input {
    margin: 10px 0;
  }
  
  .form-inline {
    flex-direction: column;
    align-items: stretch;
  }
}
</style>
</head>
<body>

<h2>Responsive Inline Form</h2>
<p>We have created an inline form that will stay horizontal until the screen width of the browser window is less than 850 pixels: then the form is displayed vertically instead of horizontally.</p>
<p>Resize the browser window to see the effect.</p>

<form class="form-inline" action="/action_page.php">
  <label for="email">Email:</label>
  <input type="email" id="email" placeholder="Enter email" name="email">
  <label for="pwd">Password:</label>
  <input type="password" id="pwd" placeholder="Enter password" name="pswd">
  <label>
    <input type="checkbox" name="remember"> Remember me
  </label>
  <button type="submit">Submit</button>
</form>