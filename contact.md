---
title: Contact
layout: page
permalink: "/contact/"
description: Contact info
---
<h3 class="t-center">For professional inquiries, contact:</h3>

<div class="t-center"> <p><strong>Jackie Williamson</strong><br /> Williamson & Holmes<br /> info@whlondon.co.uk <br /> 020 7240 0407</p> </div>

<br />

<div id="form-messages"></div>
<p class="t-center"><strong>Or, contact me directly:</strong></p>
<form id="contact-form" name="form">
<div>
<label>Name</label>
<input placeholder="Name (required)" name="name" type="text" tabindex="1" required>
</div>
<div>
<label>Email</label>
<input placeholder="E-mail (required)" name="_replyto" type="email" tabindex="2" required>
</div>
<div>
<label>Telephone</label>
<input placeholder="Tel #" type="tel" name="telephone #" tabindex="3">
</div>
<div>
<label>Message</label>
<textarea placeholder="Hi, Alex..." type="text" name="message" tabindex="4" rows="5" required></textarea>
</div>
<input type="hidden" name="_subject" value="New AlexandraDsa.com submission" />

    <input type="text" name="_gotcha" style="display:none" />
    <div>
    	<button type="submit" id="contact-submit"><i class="fa fa-envelope"></i> Send Email</button>
    </div>

</form>

<!-- Hidden message to show if contact is successful. -->
<div id="submit-success" class="collapse">
<h3 style="text-align:center;">Message received! I'll be in touch.</h3>
</div>

<!-- Hidden message to show if user encounters errors. -->
<div id="submit-errors" class="collapse">
It looks like there was an error submitting the form.
Please try again later.
</div>

<br />

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<script src="http://ajax.aspnetcdn.com/ajax/jquery.validate/1.13.1/jquery.validate.min.js"></script>
<script>
\$("#contact-form").validate({
submitHandler: function(form) {
\$.ajax({
url: "//formspree.io/dsaalexandra@gmail.com",
method: "POST",
data: {
name: $(form).find("input\[name='name'\]").val(),
_replyto: $(form).find("input\[name='_replyto'\]").val(),
message: $(form).find("textarea\[name='message'\]").val()
},
dataType: "json",
success: function() {
\$("#submit-success").fadeIn();
\$("#contact-form").fadeOut();
},
error: function() {
\$("#submit-errors").fadeIn();  
}
});
}
});
</script>