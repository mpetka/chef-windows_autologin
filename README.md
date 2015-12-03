# Windows Autologin Cookbook

[![Cookbook Version](http://img.shields.io/cookbook/v/windows_autologin.svg?style=flat-square)][cookbook]
[![Build Status](http://img.shields.io/travis/dhoer/chef-windows_autologin.svg?style=flat-square)][travis]

[cookbook]: https://supermarket.chef.io/cookbooks/windows_autologin
[travis]: https://travis-ci.org/dhoer/chef-windows_autologin

Enables/disables automatic logon using Windows 
[AutoAdminLogon](https://technet.microsoft.com/en-us/library/cc939702.aspx).
 
Automatic logon uses the domain (optional), username, and password stored in the registry to log users on to the 
computer when the system starts. The Log On to Windows dialog box is not displayed.

**WARNING:** Automatic logon allows other users to start your computer and to log on using your account. 
Also note that password is stored unencrypted under windows registry 
`HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon` when enabled.   
                                                  
## Requirements

- Chef 11.6+ (includes a built-in registry_key resource) 

### Platforms

- Windows

## Usage

Requires Administrator privileges. 

Enable automatic login for user

```ruby
# node.set['windows_autologin']['domain'] = 'domain' # optional
node.set['windows_autologin']['username'] = 'username'
node.set['windows_autologin']['password'] = 'password'

include_recipe[windows_autologin]
```

Disable automatic login and remove password entry

```ruby
node.set['windows_autologin']['enable'] = false

include_recipe[windows_autologin]
```

## Getting Help

- Ask specific questions on [Stack Overflow](http://stackoverflow.com/questions/tagged/windows_autologin).
- Report bugs and discuss potential features in
[Github issues](https://github.com/dhoer/chef-windows_autologin/issues).

## Contributing

Please refer to [CONTRIBUTING](https://github.com/dhoer/chef-windows_autologin/blob/master/CONTRIBUTING.md).

## License

MIT - see the accompanying [LICENSE](https://github.com/dhoer/chef-windows_autologin/blob/master/LICENSE.md) file
for details.
