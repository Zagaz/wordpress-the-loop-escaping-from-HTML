### An easy way to make Loops in Wordpress
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FZagaz%2Fwordpress-the-loop-escaping-from-HTML&count_bg=%233C8A7C&title_bg=%23555555&icon=wordpress.svg&icon_color=%23E7E7E7&title=Visits&edge_flat=false)](https://hits.seeyoufarm.com)

PHP has a "Escaping from HTML" feature in case of **Conditionals** and **Loops**. To read more about it, follow the [Escaping from HTML Link](https://www.php.net/manual/en/language.basic-syntax.phpmode.php "Escaping from HTML Link"). 

To use this feature in Wordpress, just take a look:

```php
<div>
	<?php if ( have_posts() ) : while ( have_posts() ) : the_post(); ?>
		//Some HTML...
	
	<?php endwhile; else : ?>
	//Some other HTML 
	
	<?php endif; ?>
</div>
```
In case of a Loop whith queries:

```php
<?php
$query_args = array(
	'post_type' => 'post',
	'posts_per_page' => '4',
);
$the_query = new WP_Query( $query_args );
?>

<div>
	<?php if ( $the_query->have_posts() ) : while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
		//Some HTML...
	
	<?php endwhile; else : ?>
	//Some other HTML 
	
	<?php endif; ?>
	<?wp_reset_postdata();?>
</div>
```





