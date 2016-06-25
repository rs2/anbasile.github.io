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
		<label class="control-label" for="inputEmail">Email</label>
		<input class="form-control" id="#inputEmail" type="email" name="_replyto" placeholder="Your email">
	    </div>
	</div>
	
	<div class="form-group">
	    <div class="col-md-12">
		<label class="control-label" for="message">Message</label>
		<textarea class="form-control" id="message" name="message" placeholder="Your message"></textarea>
	    </div>
	</div>
	
	<div class="form-group">
	 <input class="btn btn-default form-control" type="submit" value="Send">
	</div>
	
    </form>
</div>

<div class="row">
<form>
  <div class="form-group">
    <label for="exampleInputEmail1">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
  </div>
  <div class="form-group">
    <label for="exampleInputFile">File input</label>
    <input type="file" id="exampleInputFile">
    <p class="help-block">Example block-level help text here.</p>
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> Check me out
    </label>
  </div>
  <button type="submit" class="btn btn-default">Submit</button>
</form>
</div>





