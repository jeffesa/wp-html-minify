# Wordpress HTML Minify
Class to minify HTML on Wordpress without a plugin

## How I do?
- Copy the class **WP_HTML_Minify** and paste on functions.php file inside your theme.
- You need also copy and paste the code below on functions.php.
  
```php
// minify html
function wp_html_minify_finish($html){
    return new WP_HTML_Minify($html);
}

// add to buffer the wp_html_minify_start
function wp_html_minify_start(){
    ob_start('wp_html_minify_finish');
}

add_action('get_header', 'wp_html_minify_start');
