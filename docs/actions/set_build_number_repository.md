# set_build_number_repository


Set the build number from the current repository




> This action will set the **build number** according to what the SCM HEAD reports.
Currently supported SCMs are svn (uses root revision), git-svn (uses svn revision) and git (uses short hash) and mercurial (uses short hash or revision number).
There is an option, `:use_hg_revision_number`, which allows to use mercurial revision number instead of hash


set_build_number_repository |
-----|----
Supported platforms | ios, mac
Author | @pbrooks, @armadsen, @AndrewSB



**2 Examples**

```ruby
set_build_number_repository
```

```ruby
set_build_number_repository(
  xcodeproj: "./path/to/MyApp.xcodeproj"
)
```





**Parameters**

Key | Description
----|------------
  `use_hg_revision_number` | Use hg revision number instead of hash (ignored for non-hg repos)
  `xcodeproj` | explicitly specify which xcodeproj to use




<hr />
To show the documentation in your terminal, run
```no-highlight
fastlane action set_build_number_repository
```

<a href="https://github.com/fastlane/fastlane/blob/master/fastlane/lib/fastlane/actions/set_build_number_repository.rb" target="_blank">View source code</a>

<hr />

<a href="/actions"><b>Back to actions</b></a>
