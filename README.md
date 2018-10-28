# Plugin-Outlets

Generated by moving the output of the script below into common/head_tag.html
```
   #!/bin/bash
   grep -r plugin-outlet /var/www/discourse/app/|grep name|grep -o -e 'name=".*'|awk -F\" '{print $2}'|sort|uniq | while read p ; do
     echo "<script type=\"text/x-handlebars\" data-template-name=\"/connectors/$p/plugin-outlet-component\">"
     echo "<div class=\"outlet\">$p</div>"
     echo "</script>"
   done
```

