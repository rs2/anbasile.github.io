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
	    <div class="col-md-12">
		<label for="inputEmail">Email</label>
		<input class="form-control" id="#inputEmail" type="email" name="_replyto" placeholder="Your email">
	    </div>
	</div>
	
	<div class="form-group">
	    <div class="col-md-12">
		<label for="message">Message</label>
		<textarea class="form-control" id="message" name="message" placeholder="Your message"></textarea>
	    </div>
	</div>
	
	<div class="form-group">
	 <input class="btn btn-default form-control" type="submit" value="Send">
	</div>
	
    </form>
</div>





