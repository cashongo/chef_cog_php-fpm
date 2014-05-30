Description
===========

Installs and configures PHP-FPM (FastCGI Process Manager), an alternative PHP FastCGI implementation with some additional features useful for sites of any size, especially busier sites.  It's like the `unicorn` of the PHP world dawg.


Usage
=====

Creating pools in recipes
=========================
### Create PHP-FPM pool named 'www' with default settings:
```ruby
php_fpm_pool "www"
```

### Create PHP-FPM pool named 'www' with custom settings:
```ruby
php_fpm_pool "www" do
  cookbook "another-cookbook" # get template from another cookbook
  process_manager "dynamic"
  max_requests 5000
  php_options 'php_admin_flag[log_errors]' => 'on', 'php_admin_value[memory_limit]' => '32M'
end
```

### Delete PHP-FPM pool named 'www':
```ruby
php_fpm_pool "www" do
  enable false
end
```