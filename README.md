# 4d-plugin-role-handlers
Set or get the default application, by scheme, UTI or extension. Also obtain list of capable applications.

##Platform

| carbon | cocoa | win32 | win64 |
|:------:|:-----:|:---------:|:---------:|
|🆗|🆗|🚫|🚫|

Commands
---

```c
// --- Role Handlers
Get_default_application
Set_default_application
Get_capable_applications
```

![](https://github.com/miyako/4d-plugin-role-handlers/blob/master/images/change.png)

Examples
---

```
  //passing a URL scheme
$error:=Get default application ("mailto";$id;$path)
$error:=Get default application ("http";$id;$path)
$error:=Get default application ("ftp";$id;$path)

  //passing a uti
$error:=Get default application ("public.png";$id;$path)
$error:=Get default application ("public.text";$id;$path)
$error:=Get default application ("com.4d.4d.blob";$id;$path)

  //passing an extension
$error:=Get default application ("png";$id;$path)
$error:=Get default application ("text";$id;$path)
$error:=Get default application ("4dd";$id;$path)

  //passing a MIME
$error:=Get default application ("text/html";$id;$path)
$error:=Get default application ("text/plain";$id;$path)
$error:=Get default application ("image/png";$id;$path)

  //likewise
$error:=Get capable applications ("mailto";$ids;$paths)
$error:=Get capable applications ("http";$ids;$paths)

  //setter (pass scheme, uti or extension in $1; $2 is always bundle id) 
For ($i;1;Size of array($ids))
$error:=Set default application ("http";$ids{$i})
OPEN WEB URL("http://www.4d.com")
End for
```
