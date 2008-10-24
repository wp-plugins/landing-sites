=== Landing sites ===
Contributors: The undersigned, devil1591, gonzague, orion
Donate link: 
Tags: google, referer, related
Requires at least: 2.0.2
Tested up to: 2.7-almost-beta
Stable tag: trunk

When visitors is referred to your site from a search engine, the plugin is showing them related posts to their search on your blog.

== Description ==

When visitors is referred to your site from a search engine, they are definitely looking for something specific - often they just roughly check the page they land on and then closes the window if what they are looking for isn't there. Why not help them by showing them related posts to their search on your blog? This plugin/guide lets you do that, works with a long list of search engines! Plugin is made with help from these scripts: http://www.w-a-s-a-b-i.com/archives/2006/02/02/wordpress-related-entries-20/ - http://textsnippets.com/posts/show/231 - http://www.lazaryn.com/entry-28.html

== Installation ==

1. Upload the folder `landing-sites` to your `/wp-content/plugins/` directory

2. Activate the plugin

3. Where you want to show the related posts list, add this code:

<?php if (ls_getinfo(‘isref’)) : ?>
   <h2><?php ls_getinfo(‘terms’); ?></h2>
   <p>You came here from <?php ls_getinfo(‘referrer’); ?> searching for <i><?php ls_getinfo(‘terms’); ?></i>. These posts might be of interest:</p>
   <ul>
     <?php ls_related(5, 10, ‘<li>’, ‘</li>’, ”, ”, false, false); ?>
   </ul>   
<?php endif; ?>

== Details on functions ==

ls_getinfo(’isref’)
Returning true if the referrer is a supported search engine - used as a conditional tag

ls_getinfo(’terms’)
Outputs the search terms

ls_getinfo(’referrer’)
Outputs a link to the referring search engine

ls_related()
Outputs the list of related posts. This can be customized by passing variables to it. ls_related(limit, lenght, ‘before title’, ‘after title’, ‘before post’, ‘after post’ show password protected posts, show post excerpts).

In the code example in step 3 of the installation, it outputs 5 related posts, 10 words per excerpt (if excerpts are enabled), list item start before title, list item close after post title, no content before and after posts, doesn’t show password protected posts and doesn’t show excerpts.

== Frequently Asked Questions ==

== Screenshots ==

1. A website showing related post when a visitor has searched for "landing sites screenshot"