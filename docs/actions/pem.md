# pem


Makes sure a valid push profile is active and creates a new one if needed




> Additionally to the available options, you can also specify a block that only gets executed if a new
profile was created. You can use it to upload the new profile to your server.
Use it like this: 
pem(
  new_profile: proc do 
    # your upload code
  end
)


pem |
-----|----
Supported platforms | ios
Author | @KrauseFx



**2 Examples**

```ruby
pem
```

```ruby
pem(
  force: true, # create a new profile, even if the old one is still valid
  app_identifier: "net.sunapps.9", # optional app identifier,
  save_private_key: true,
  new_profile: proc do |profile_path| # this block gets called when a new profile was generated
    puts profile_path # the absolute path to the new PEM file
    # insert the code to upload the PEM file to the server
  end
)
```





**Parameters**

Key | Description
----|------------
  `development` | Renew the development push certificate instead of the production one
  `generate_p12` | Generate a p12 file additionally to a PEM file
  `active_days_limit` | If the current certificate is active for less than this number of days, generate a new one. Default value is 30 days
  `force` | Create a new push certificate, even if the current one is active for 30 (or PEM_ACTIVE_DAYS_LIMIT) more days
  `save_private_key` | Set to save the private RSA key
  `app_identifier` | The bundle identifier of your app
  `username` | Your Apple ID Username
  `team_id` | The ID of your Developer Portal team if you're in multiple teams
  `team_name` | The name of your Developer Portal team if you're in multiple teams
  `p12_password` | The password that is used for your p12 file
  `pem_name` | The file name of the generated .pem file
  `output_path` | The path to a directory in which all certificates and private keys should be stored
  `new_profile` | Block that is called if there is a new profile




<hr />
To show the documentation in your terminal, run
```no-highlight
fastlane action pem
```

<a href="https://github.com/fastlane/fastlane/blob/master/fastlane/lib/fastlane/actions/pem.rb" target="_blank">View source code</a>

<hr />

<a href="/actions"><b>Back to actions</b></a>
