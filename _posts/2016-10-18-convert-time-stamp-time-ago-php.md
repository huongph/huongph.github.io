---
layout: blogs_singles
thumbnail: http://phppot.com/wp-content/uploads/2016/03/php-time-ago-function.png
title: PHP - Time Ago PHP Function.
description:  The following function will convert the time stamp to time ago like 1hour ago, 1day ago, 2days ago etc.
date: 18 Oct 2016
author: Huongph
---

The following function will convert the time stamp to time ago like 1hour ago, 1day ago, 2days ago etc.

{% highlight javascript %}
{% raw %}
<?php
	function timeAgo($time_ago){
		$cur_time 	= time();
		$time_elapsed 	= $cur_time - $time_ago;
		$seconds 	= $time_elapsed ;
		$minutes 	= round($time_elapsed / 60 );
		$hours 		= round($time_elapsed / 3600);
		$days 		= round($time_elapsed / 86400 );
		$weeks 		= round($time_elapsed / 604800);
		$months 	= round($time_elapsed / 2600640 );
		$years 		= round($time_elapsed / 31207680 );
		// Seconds
		if($seconds <= 60){
			echo "$seconds seconds ago";
		}
		//Minutes
		else if($minutes <=60){
			if($minutes==1){
				echo "one minute ago";
			}
			else{
				echo "$minutes minutes ago";
			}
		}
		//Hours
		else if($hours <=24){
			if($hours==1){
				echo "an hour ago";
			}else{
				echo "$hours hours ago";
			}
		}
		//Days
		else if($days <= 7){
			if($days==1){
				echo "yesterday";
			}else{
				echo "$days days ago";
			}
		}
		//Weeks
		else if($weeks <= 4.3){
			if($weeks==1){
				echo "a week ago";
			}else{
				echo "$weeks weeks ago";
			}
		}
		//Months
		else if($months <=12){
			if($months==1){
				echo "a month ago";
			}else{
				echo "$months months ago";
			}
		}
		//Years
		else{
			if($years==1){
				echo "one year ago";
			}else{
				echo "$years years ago";
			}
		}
	}

?>

{% endraw %}
{% endhighlight %}

How to use it:

{% highlight javascript %}
{% raw %}
   <?php
	  $curenttime="2013-07-10 09:09:09";
	  $time_ago =strtotime($curenttime);
	  echo timeAgo($time_ago);
  ?>
{% endraw %}
{% endhighlight %}

