---
layout: page
title: contact
permalink: /contact/
---

<div class="row">
    <form action="https://formspree.io/{{ site.email }}" method="POST">

	<div class="form-group" style="width: 100%">
	    <label for="inputEmail">Email</label>
	    <input id="#inputEmail" type="email" name="_replyto" placeholder="Your email">
	</div>
	
	<div class="form-group">
	    <label for="message">Message</label>
	    <textarea id="message" name="message" placeholder="Your message"></textarea>
	</div>
	<div class="form-group">
	    <input type="hidden" name="_next" value="{{ site.baseurl}}/thanks/" />
	    <input type="hidden" name="_subject" value="Website contact" />
	    <input type="text" name="_gotcha" style="display:none" />
	    <input type="submit" value="Send" class="btn btn-default">
	</div>
    </form>
</div>





