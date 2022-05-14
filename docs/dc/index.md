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
	



<style>
body {font-family: Arial, Helvetica, sans-serif;}
* {box-sizing: border-box;}

input[type=text], select, textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

input[type=submit] {
  background-color: #04AA6D;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}

.container {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>

<!-- modify this form HTML and place wherever you want your form -->
  <form class="form" id="fs-frm" name="simple-contact-form" accept-charset="utf-8" action="https://formspree.io/f/mnqlleyl" method="post">
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
