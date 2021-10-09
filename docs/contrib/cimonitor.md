<!-- DO NOT EDIT THIS FILE! -->
<!-- Instead edit contrib/cimonitor.php -->
<!-- Then run bin/docgen -->

# cimonitor

[Source](/contrib/cimonitor.php)


# CIMonitor recipe

Monitor your deployments on [CIMonitor](https://github.com/CIMonitor/CIMonitor).

![CIMonitorGif](https://www.steefmin.xyz/deployer-example.gif)

Require cimonitor recipe in your `deploy.php` file:

```php
require 'contrib/cimonitor.php';
```

Add tasks on deploy:

```php
before('deploy', 'cimonitor:notify');
after('deploy:success', 'cimonitor:notify:success');
after('deploy:failed', 'cimonitor:notify:failure');
```

## Configuration

- `cimonitor_webhook` – CIMonitor server webhook url, **required**
  ```
  set('cimonitor_webhook', 'https://cimonitor.enrise.com/webhook/deployer');
  ```
- `cimonitor_title` – the title of application, default the username\reponame combination from `{{repository}}`
  ```
  set('cimonitor_title', '');
  ```
- `cimonitor_user` – User object with name and email, default gets information from `git config`
  ```
  set('cimonitor_user', function () {
    return [
      'name' => 'John Doe',
      'email' => 'john@enrise.com',
    ];
  });
  ```

Various cimonitor statusses are set, in case you want to change these yourselves. See the [CIMonitor documentation](https://cimonitor.readthedocs.io/en/latest/) for the usages of different states.

## Usage

If you want to notify only about beginning of deployment add this line only:

```php
before('deploy', 'cimonitor:notify');
```

If you want to notify about successful end of deployment add this too:

```php
after('deploy:success', 'cimonitor:notify:success');
```

If you want to notify about failed deployment add this too:

```php
after('deploy:failed', 'cimonitor:notify:failure');
```



## Configuration
### cimonitor_title
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L70)

Title of project based on git repo



### cimonitor_user
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L75)





### cimonitor_status_info
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L83)

CI monitor status states and job states

```php title="Default value"
'info'
```


### cimonitor_status_warning
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L84)



```php title="Default value"
'warning'
```


### cimonitor_status_error
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L85)



```php title="Default value"
'error'
```


### cimonitor_status_success
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L86)



```php title="Default value"
'success'
```


### cimonitor_job_state_info
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L87)



```php title="Default value"
get('cimonitor_status_info')
```


### cimonitor_job_state_pending
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L88)



```php title="Default value"
'pending'
```


### cimonitor_job_state_running
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L89)



```php title="Default value"
'running'
```


### cimonitor_job_state_warning
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L90)



```php title="Default value"
get('cimonitor_status_warning')
```


### cimonitor_job_state_error
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L91)



```php title="Default value"
get('cimonitor_status_error')
```


### cimonitor_job_state_success
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L92)



```php title="Default value"
get('cimonitor_status_success')
```



## Tasks

### cimonitor:notify
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L95)

Notifying CIMonitor.




### cimonitor:notify:success
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L122)

Notifying CIMonitor about deploy finish.




### cimonitor:notify:failure
[Source](https://github.com/deployphp/deployer/blob/master/contrib/cimonitor.php#L151)

Notifying CIMonitor about deploy failure.



