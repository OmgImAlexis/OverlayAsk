OverlayAsk
========

Add this to your HTML and add your description, etc. to the askbox part in the customise menu then add the .overlay_ask to the link you want to use for it.

```html
<meta name="text:askbox" content="" />
<script type="text/javascript">
$(document).ready(function() {
	$('.overlay_ask').on('click', function(){
		if ($('#overlay').is(":hidden")) {
			$('#tumblr_controls').css('z-index', 1);
			$('html').css("overflow", "hidden");
			$('body').css("overflow", "hidden");
			$('#overlay').show();
			return false;
		}
	});
	$('body').on('click', function(){
		if ($('#overlay').is(":visible")) {
			$('#tumblr_controls').css('z-index', 999999999999999999);
			$('html').css("overflow-y", "auto");
			$('body').css("overflow-y", "auto");
			$('#overlay').hide();
			return false;
		}
	});
});
</script>
<div id="overlay" style="position: fixed; top: 0px; right: 0px; bottom: 0px; left: 0px; z-index: 999999; display: none;">
	<div id="background" style="position: fixed; top: 0; right: 0; bottom: 0; left: 0; background: #000; opacity: .75;"></div>
	<div style="padding: 10px; width: 500px; height: 220px; background: #fff;position: absolute; left: 50%; top: 50%;  margin-left: -250px; margin-top: -100px;">
		<p>{text:askbox}</p>
		<p><iframe frameborder="0" width="500" height="190" src="http://tumblr.com/ask_form/reblogalert.tumblr.com"></iframe></p>
	</div>
</div>
```
