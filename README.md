### An easy way to make Loops in Wordpress

PHP has a "Escaping from HTML" feature in case of ** Conditionals **and **Loops**. To read more about it, follow the [Escaping from HTML Link](https://www.php.net/manual/en/language.basic-syntax.phpmode.php "Escaping from HTML Link"). 

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
	<?php if ( have_posts() ) : while ( have_posts() ) : the_post(); ?>
		//Some HTML...
	
	<?php endwhile; else : ?>
	//Some other HTML 
	
	<?php endif; ?>
	<?wp_reset_postdata();?>
</div>
```





