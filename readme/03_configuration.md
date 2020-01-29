## Configuration

__signalk-notification-injector__ is configured through the Signal K
Node server plugin configuration interface.
Navigate to _Server->Plugin config_ and select the _Notification injector_ tab.

![Plugin configuration screen](readme/screenshot.png)

The _Active_ checkbox tells the Signal K Node server whether or not to run the
plugin: on first execution you should check this, before reviewing and
amending the configuration options discussed below.
Changes you make will only be saved and applied when you finally click the
_Submit_ button.

The plugin configuration pane has the following entries.

### FIFO path

This specifies the filename of the named pipe or FIFO.  When the plugin
starts it will check for the presence of this file and, if necessary,
attempt to create it by a call to mkfifo(1).

The default value is ```/var/signalk-injector```.

### Passwords

This is a whitespace delimited list of password tokens that will allow
processing of an incoming message.

The default value is "letmein 0000".  You should change this.

### Default notification path

If a message doesn't specify a key path, then the requested key will be
created under the path specified here.  The specified path must begin
with "notifications.".

The default value is "notifications.injector." which means that simple
keys will be placed under the path ```vessels.self.notifications.injector.```. 

### Default notification state

Defines the value to be used for the notification state field if no value
is specified in a message.

The default value is 'alert'.

### Default notification methods

Defines the values to be used for the notification methods field if no values
are specified in a message.

The default value is "visual sound".