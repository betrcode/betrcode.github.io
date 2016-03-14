---
layout: post
title: "Don't Repeat Yourself in PLSQL parameters"
tags: [oracle, plsql]
comments: []
---
<!--more-->

When writing PLSQL in the Oracle database, you define parameters to a function/procedure like this:

{% highlight sql %}
FUNCTION getFullName(iUserId IN INTEGER) RETURN VARCHAR2
IS
BEGIN
   --TODO: Implement this
   RETURN "";
END getFullname;
{% endhighlight %}

Instead of writing it like that, consider using a table.column definition as type for your parameter! This way, if you change your table, you will not also have to change your code!

Example:
{% highlight sql %}
FUNCTION getFullName(iUserId IN SIGNUP.ID%TYPE) RETURN VARCHAR2
IS
BEGIN
   --TODO: Implement this
   RETURN "";
END getFullname;
{% endhighlight %}

Now, if you for some reason change the ID column in the SIGNUP table to be something other than INTEGER, you can leave the code as is! Much more DRY!
