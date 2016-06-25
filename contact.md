---
layout: page
title: contact
permalink: /contact/
---

<div class="row">
    <form action="https://formspree.io/{{ site.email }}" method="POST">
	<div class="form-group">
	    <input type="email" name="_replyto" placeholder="Your email">
	</div>
	<div class="form-group">
	    <textarea name="message" placeholder="Your message"></textarea>
	</div>
	    <input type="hidden" name="_next" value="{{ site.baseurl}}/thanks/" />
	    <input type="hidden" name="_subject" value="Website contact" />
	    <input type="text" name="_gotcha" style="display:none" />
	<input type="submit" value="Send" class="btn btn-default">
    </form>
</div>





