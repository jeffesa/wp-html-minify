# Wordpress HTML Minify
Class to minify HTML on Wordpress without a plugin

## Getting started
- Copy the class **WP_HTML_Minify** and paste on functions.php file inside your theme.
- **Discuss:** Conversations and discussions take place in 
  
<!-- language: php -->
// minify html
function wp_html_minify_finish($html){
    return new WP_HTML_Minify($html);
}

// add to buffer the wp_html_minify_start
function wp_html_minify_start(){
    ob_start('wp_html_minify_finish');
}
add_action('get_header', 'wp_html_minify_start');
