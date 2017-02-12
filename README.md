# Installing ChatCenter iO for Web
## Table of Contents
1. [Quick Start Guide / Installing ChatCenter iO on your Project](#quickstart)
2. [Install your snippet](#install)
3. [Customize](#customize)

## Quick Start Guide / Installing ChatCenter iO on your Project<a name="quickstart"></a>

The quick start can be done like this process:

On the ChatCenter iO’s website

1. Create your account on the ChatCenteriO's website,
2. Access to the ChatCenteriO's dashboard to get your APP_TOKEN and embedding snippet 
 * Access following contents. Dashboard -> Platform Integrations -> Website
 * Select the team which you want to integrate to your website.
 * Copy the snippet code from the screen.

4. Install the snippet code into your web pages.

## Install your snippet<a name="install"></a>

#### Unidentified Users
Install for leads visiting logged-out pages
Use on pages where you want to have conversations with logged-out visitors to your site.
    
	<script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='APP_TOKEN' data-org-uid='TEAM_NAME' data-style='popup'>
</script> 

#### Identified Users
Install for users on logged-in pages
Needed on pages where you want to track data  have in-app conversations with logged-in users of your site.

##### Example code for ERB in Rails (Ruby)

```
<script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='<%= current_user.name %>',
	data-user-email='<%= current_user.email %>',
	data-user-createdat='<%= current_user.created_at.to_i %>'></script>
```	

##### Example code for Django (Python)
```
<script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='{{ request.user.name }}',
	data-user-email='{{ request.user.email }}',
	data-user-createdat='{{ request.user.date_joined | date: "U" }}'></script>
```	

##### Example code for PHP
```
<script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='<?php echo $current_user->name ?>',
	data-user-email='<?php echo $current_user->email ?>',
	data-user-createdat='<?php echo strtotime($current_user->created_at) ?>'></script>
```

##### Parameters

Parameter name|Description
---|---
data-app-token     | Replace with Your APP_TOKEN provided in your dashboard.
data-org-uid       | Replace with your ORG_UID of your “My First Team”.
data-style         | Select widget style. “popup”(popup-window chat) <br>or “normal”(Inside-window chat)
deta-user-fullname | Customer's full name.
data-user-email| Customer’s email.
data-user-createdate| Customer's creation date


## Customize<a name="customize"></a>

You can customize your widget by embedding the following css within your html file.

#### Replace the image for "Open chat ICON"

``` 
<style type="text/css">
  #cw-root #cw-button-open-widget {
    background: url("[ICON_IMAGE_URL") !important;
  }
</style>
```

#### Change "Open chat ICON" size
```
<style type="text/css">
  #cw-root #cw-button-open-widget {
    width: 40px !important;;
    height: 40px !important;;
    background-size:40px !important;
  }
</style>
```

### Change "Open chat ICON" position
```
<style type="text/css">
  #cw-root #cw-button-open-widget {
    position: fixed !important;
    right: 20px !important;
    bottom: 20px !important;
  }
</style>
```

### If you need specify different styles for PC and Mobiles
```
<style type="text/css">
  #cw-root #cw-button-open-widget {
    @media (max-width: $screen-md-min) {
      // For mobile & tablet
    }

    @media (min-width: $screen-md-min) {
      // For PC
    }
  }
</style>
```



