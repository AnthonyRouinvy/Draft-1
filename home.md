<!-- TITLE: Home -->
<!-- SUBTITLE: A quick summary of Home -->

# Wiki Docs
Documentation d'usage pour le code

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

Code en PHP
```<?php 
	add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
	function theme_enqueue_styles() { 
		wp_enqueue_style( 'parent-style', get_template_directory_uri() . '/style.css' ); } 
    
    function header_widgets_init() {
 
    register_sidebar( array(

    'name' => 'Widget supplementaire',
    'id' => 'new-widget-area',
    'before_widget' => '<div class="nwa-widget">',
    'after_widget' => '</div>',
    'before_title' => '<h2 class="nwa-title">',
    'after_title' => '</h2>',
    ) );
    }

add_action( 'widgets_init', 'header_widgets_init' );
```
