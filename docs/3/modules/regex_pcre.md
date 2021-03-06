---
title: "Module Details: regex_pcre (v3)"
---

## The "regex_pcre" Module

!!! note ""
    This module depends on a third-party library ([PCRE](https://www.pcre.org)) and must be manually enabled at compile time.

    Once you have installed the dependency you can enable this module using the following command:

    <pre><code>./configure --enable-extras regex_pcre</code></pre>

### Description

This module provides the `pcre` regular expression engine which uses the [PCRE](https://www.pcre.org) library.

### Configuration

To load this module use the following `<module>` tag:

```xml
<module name="regex_pcre">
```

This module requires no other configuration.
