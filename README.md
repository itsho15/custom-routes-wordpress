# custom-routes-wordpress
add custom routes to wordpress plugin or theme

how to use

add this line to your functions.php in theme

require_once get_template_directory . '/routes/web.php';
examples in web.php

require_once 'route.php';
$route = new Route();
// example class function

this class in my theme App\Http\Controllers\RegisterShortcodeController change it with your own 

$route->add('name/.+/.+', array('\App\Http\Controllers\RegisterShortcodeController', 'test')); // class RegisterShortcodeController and method = test
// example anony function
$route->add('/name/.+', function ($name) {
	echo "Name $name";
});
// example anony function
$route->add('/this/is/the/.+/story/of/.+', function ($first, $second) {
	echo "This is the $first story of $second";
});
$route->listen();
