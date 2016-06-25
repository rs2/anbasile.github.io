---
layout: page
title: contact
permalink: /contact/
---

<div class="row">
<form action="https://formspree.io/{{ site.email }}" method="POST">
	<input type="hidden" name="_next" value="{{ site.baseurl}}/thanks/" />
	<input type="hidden" name="_subject" value="Website contact" />
	<input type="text" name="_gotcha" style="display:none" />
  <div class="form-group">
    <label for="InputEmail1">Email address</label>
    <input type="email" class="form-control" id="InputEmail1" name="_replyto" placeholder="Your email">
  </div>
  
    <div class="form-group">
    <label for="message">Message</label>
    <textarea class="form-control" id="message" placeholder="Your message" name="message"></textarea>
  </div>

  <button type="submit" class="btn btn-default">Send</button>
</form>
</div>





