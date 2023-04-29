# WPRemoveUserCapabilities
WordPress remove user capability

```PHP
/**
 * Remove capabilities from editors.
 *
 * Call the function when your plugin/theme is activated.
 */
function wpcodex_set_capabilities() {
 
    // Get the role object.
    $editor = get_role( 'editor' );
 
    // A list of capabilities to remove from editors.
    $caps = array(
        'moderate_comments',
        'manage_categories',
        'manage_links',
        'edit_others_posts',
        'edit_others_pages',
        'delete_posts',
    );
 
    foreach ( $caps as $cap ) {
     
        // Remove the capability.
        $editor->remove_cap( $cap );
    }
}
add_action( 'init', 'wpcodex_set_capabilities' );
```

<br />source: 
<br />https://developer.wordpress.org/reference/classes/wp_role/remove_cap/
