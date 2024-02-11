<?php
/*
Plugin Name: Show Page Slug in Admin
Plugin URI: https://mytchall.dev/projects/wordpress-show-page-slug-in-admin/
Description: Adds a 'permalink' column to display the page slug on the Pages screen.
Version: 1.0
Requires PHP: 7.4
Author: Mytchall Bransgrove
Author URI: https://mytchall.dev
License: GPLv2 or later
*/

if ( ! defined( 'ABSPATH' ) ) exit;

add_filter('manage_page_posts_columns', 'spsia_custom_column', 10);
add_action('manage_page_posts_custom_column', 'spsia_add_custom_column', 10, 2);

function spsia_custom_column($defaults) {

  $new = array();
  foreach ($defaults as $key => $value) {
      // Adds the permalink column before the author
      if ($key === 'author') {
          $new['url'] = 'Permalink';
      }
      $new[$key] = $value;
  }
  return $new;
}

function spsia_add_custom_column($column_name, $post_id) {
  if ($column_name == 'url') {
    echo esc_url(wp_make_link_relative(get_permalink($post_id)));
  }
}

?>