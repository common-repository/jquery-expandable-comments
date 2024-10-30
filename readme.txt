=== jQuery Comment Replies ===
Contributors: doodlebee
Donate link: http://brassblogs.com/donate
Tags: jQuery, comments, expand, replies
Requires at least: 3.0
Tested up to: 3.9
Stable tag: 1.2.4
License: GPLv2 or later

Make your multi-level comment replies show on demand with a slick jQuery slideToggle() action.


== Description ==

Simple plugin to show/hide comment replies, rather than have them all listed.  An options page makes it really easy to change different parts of your comment calls.


= Features =
This keeps the default "[`wp_list_comments()`](http://codex.wordpress.org/Function_Reference/wp_list_comments)" features.  A clickable span that triggers the action to expand the replies is also added.  

New features are including easing options, as well as allowing images. An options page has been added for further customizations, making it even easier to use.


== Installation ==

1. Unzip the package. 
2. Upload to your plugins directory. 
3. Go to "Plugins" and activate.


= Options Page =
The items you can mess with here will edit the arguments for wp_list_comments(), so you no longer need to add arguments to your call. In fact, if you have arguments in your bb_list_comments call, they will be ignored (but if they are there, it won't break anything).  The only sections to comment on (because they are not a part of the Codex) are:

* Show Replies Text/Hide Replies Text.  These items are the text you set for the show/hide links.  

* Stylesheets.  The plugin will see what theme you are using.  If you're using a default WordPress theme, then styles will be applied that match your active theme. Otherwise, no styles will be applied. You can go to the wp-content/plugins/jquery-expandable-comments/css folder and use any of these stylesheets as a reference to style it yourself in your own theme stylesheet.

* Slide Speed (both open and close).  This is the speed of the animation for opening and closing the replies.  You can use "fast" or "slow"; or set how long (in milliseconds) you want the animation to take.

* Easing Type.  The jQuery Easing plugin has been added so you have more animation options.  Simply choose which animation you want to use, and it will be applied to both the opening and closing of replies.

I'll also comment on the "callback" section - it is discussed in the codex, but there's no example of how to use it.  If you want to format the layout of your comments, then you need to use a callback function to rearrange the HTML.  This plugin comes with a callback function you can use.  It's NOT set as the default.  If you'd like to use it, enter in `bb_jcr_format_comment` to this text field, and your comment layout will use the callback supplied in the plugin.  if you still want to edit the layout, feel free to copy the function (located within jQuery-comments.php, around line 73) and paste it into your theme's functions.php file.  You WILL have to rename the function, or you'll get a fatal error.  Once you rename the function, take that name and pop it into the "callback" field on the settings page, then feel free to edit the function to get the exact layout you want to have.

There's several tutorials available for how to edit the comment layout, but [Jeremy Clark](http://clark-technet.com/2008/11/wordpress-27-comment-callback-function)'s is the one that actually started this plugin.


== Frequently Asked Questions ==  

= How do I use an image for the Show/Hide Replies text? =
If you want to use an image in place of (or with) the text, then use CSS to pull that off (this example has the image, named "sprite.png", uploaded to the theme's images directory).  An example:

`.replylink span {
	display:inline-block;
	background:url("images/sprite.png") no-repeat left top;
	width:20px;
	height:20px;
	overflow:hidden;
	line-height:50px; /* make text disappear */
}`

= No other questions at this time. =
But if you have any, by all means, feel free to ask away.  I'd also love input on features you'd like added or things you'd like to see to improve this plugin.  See the "Other Notes" section on how to contact me.

Please also note that, even though I have a disclaimer about my limited availability to assist, I ALWAYS try to help out as much as I can - which is evidenced by the "Support" thread.  WordPress does *not* give me any notice whensomeone leaves a support question on the forums - you have to rely on me having the time to come in and check - and these days that's not often.  I try to get in to check as often as I can, but if it's been more than a week since you've left a question on support, please email me so I can try to help you out.

And PLEASE do not leave support questions in the "reviews" section.  If I help you out and solve your problem (which is usually the case) you *cannot* change your review.  I've found, lately, that a lot of people are having a problem, leaving a bad review and terrible rating, and then I solve the problem (and it usually turns out it's not my plugin that was the issue in the first place).  That doesn't help anyone.  Please leave support questions in the support forum section, and actual reviews in the "reviews" section.  Thank you.


== Screenshots ==

1. Closed Replies (hidden) Example
2. Open Replies (show) Example


== Changelog ==

= 1.2.4 =
* further troubleshooting issues with bb-toggle-kids.js - issues repaired.
* tested in default WordPress themes from Twenty Ten to Twenty Fourteen.
* edited and streamlined options page a bit
* deprecated the "Callback" in the options page. You can still use it, but I'd move away from it - the next release will probably only have it as a reference and not use it at all.

= 1.2.2 =
* further troubleshoting issues with the repository.  Discovered the CDN is not allowed to be added to the plugin, so have reverted back to including the jQuery easing js file.

= 1.2.1 =
* had some issues with updating the WordPress repository (for some reason, wouldn't upload certain files, refused to delete others). Finally got it all sorted.  Sorry for the delay.

= 1.2 =
* removed local jquery easing library, reverted to cdn
* edited script to work with TwentyThirteen (TwentyThirteen renamed the 'li.commentlist' to 'li.comment-list')
* added previously unavailable "div" option.
* fixed script localization
* removed the necessity of rewriting the Walker_Comment class.  This renders the use of bb_list_comments() unneccessary.
* previously, there were no styles set for this plugin, but due to popular demand, I've put in a default stylesheet.
* finally actually figured out how to set up translation correctly. Yay! pot/mo files added.

= 1.1 =
* fixed a bug when clicking show/hide made the child divs "bounce"

= 1.0 =
* Newly revamped code, been rewritten for Wordpress 3.5 and cleaned up a bit.
* Options page added to make it really easy to edit text, animations, and speed, as well as making other options for wp_list_comments easy to manage.

= 0.3 =
* Edited code to better detect what Pages/posts to add the script on.
* Added text changing functionality to the "Show/Hide Replies" link, so now it'll say "Show Replies" when child comments are closed, and "Hide Replies" when they are open.

= 0.2.1 = 
* Edited readme file and stable version of plugin.

= 0.2 = 
* Upgraded for 3.1 usage
* cleaned up/streamlined/updated code
* made it easier - no more renaming/moving files around. Simply upload and activate.
* no extra javascript files - uses WP's system instead. 

= 0.1 = 
* First release.


== Upgrade Notice ==

= 1.2.3 = 
** IMPORTANT ** bb_list_comments() is now deprecated.  You WILL need to switch back to wp_list_comments() in your theme files.  This should fix the old conflict issue with Spam Free WordPress.

I sincerely apologize for the issus with the plugin for the past couple of releases.  I had a bit of trouble with the repository, and now all the issues have been resolved.


== Other Info ==

= Known Issues =

None at this time.

[Contact Shelly](http://brassblogs.com/contact)

Given that this is free, I offer limited support. If you have issues with the plugin *working* I will do whatever I can to help you fix the issue, but when it comes to customization, I'm in limited supply.  I'll do what I can, but no guarantees.  This is your standard "as is" application.  In all honesty, ask customization questions in the forums - if I can't help, perhaps someone else can.  (If you want to hire me to customize it, that's another story - feel free to contact me to do so!)

PLEASE NOTE that the WordPress support system DOES NOT notify me when someone leaves a support question.  It requires me to come back and check manually to see if anyone has had an issue.  Sometimes, I don't get to do that for a while.  If you left a support request on the forums, and it's been at least a week since you left it with no response, please drop me an email to let me know so I can attempt to help you out.  I'm pretty good at helping out - but I'm not so good at coming to check the forums - especially when I'm busy with client work.
