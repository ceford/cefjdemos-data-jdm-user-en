<!-- Filename: Standard_Module_Chromes / Display title: Standard Module Chromes -->

Note that this example includes class additions because the examples are
taken using mod_mainmenu. The suffix "\_menu" to the div class and the
"menu" class on the ul tag are not present with other modules.

**Comparison of the Joomla! standard Module chromes** These are the same
from Joomla! 1.5 through 3.x

<table style="width:100%" class="wikitable">
<caption><b>Comparison of the Joomla! standard Module chromes</b>
These are the same from Joomla! 1.5 through 3.x
</caption>
<tbody><tr>
<th width="100">Style
</th>
<th>Output
</th>
<th width="210">Appearance
</th></tr>
<tr>
<th>rounded<br>
</th>
<td><div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;div class="module_menu"&gt;
  &lt;div&gt;
    &lt;div&gt;
      &lt;div&gt;
        &lt;h3&gt;Main Menu&lt;/h3&gt;
        &lt;ul class="menu"&gt;
          &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
        &lt;/ul&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;</pre></div>
</td>
<td><img alt="Module chrome rounded.png" src="https://docs.joomla.org/images/8/8d/Module_chrome_rounded.png" decoding="async" data-file-width="204" data-file-height="190" width="204" height="190">
</td></tr>
<tr>
<th>none
</th>
<td><div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;ul class="menu"&gt;
  &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
&lt;/ul&gt;</pre></div>
</td>
<td>
<p><img alt="Module chrome none.png" src="https://docs.joomla.org/images/1/18/Module_chrome_none.png" decoding="async" data-file-width="204" data-file-height="150" width="204" height="150">
</p>
</td></tr>
<tr>
<th>table
</th>
<td><div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;table cellpadding="0" cellspacing="0" class="moduletable_menu"&gt;
  &lt;tr&gt;
    &lt;th valign="top"&gt;Main Menu&lt;/th&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
    &lt;td&gt;
      &lt;ul class="menu"&gt;
        &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/td&gt;
  &lt;/tr&gt;
&lt;/table&gt;</pre></div>
</td>
<td><img alt="Module chrome table.png" src="https://docs.joomla.org/images/9/9d/Module_chrome_table.png" decoding="async" data-file-width="204" data-file-height="160" width="204" height="160">
</td></tr>
<tr>
<th>horz
</th>
<td><div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;table cellspacing="1" cellpadding="0" border="0" width="100%"&gt;
  &lt;tr&gt;
    &lt;td valign="top"&gt;
      &lt;table cellpadding="0" cellspacing="0" class="moduletable_menu"&gt;
        &lt;tr&gt;
          &lt;th valign="top"&gt;Main Menu&lt;/th&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
          &lt;td&gt;
            &lt;ul class="menu"&gt;
              &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
            &lt;/ul&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/table&gt;
    &lt;/td&gt;
  &lt;/tr&gt;
&lt;/table&gt;</pre></div>
</td>
<td><img alt="Module chrome horz.png" src="https://docs.joomla.org/images/2/24/Module_chrome_horz.png" decoding="async" data-file-width="204" data-file-height="170" width="204" height="170">
</td></tr>
<tr>
<th>xhtml
</th>
<td><div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;div class="moduletable_menu"&gt;
  &lt;h3&gt;Main Menu&lt;/h3&gt;
  &lt;ul class="menu"&gt;
    &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;</pre></div>
</td>
<td><img alt="Module chrome xhtml.png" src="https://docs.joomla.org/images/8/83/Module_chrome_xhtml.png" decoding="async" data-file-width="206" data-file-height="165" width="206" height="165">
</td></tr>
<tr>
<th>html5
</th>
<td>
<div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;div class="well _menu"&gt;
  &lt;h3 class="page-header"&gt;Main Menu&lt;/h3&gt;
  &lt;ul class="nav menu"&gt;
    &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;</pre></div>
</td>
<td><img alt="Module chrome html5.png" src="https://docs.joomla.org/images/9/9f/Module_chrome_html5.png" decoding="async" data-file-width="227" data-file-height="205" width="227" height="205">
</td></tr>
<tr>
<th>outline
</th>
<td><div class="mw-highlight mw-highlight-lang-html mw-content-ltr" dir="ltr"><pre>&lt;div class="mod-preview"&gt;
  &lt;div class="mod-preview-info"&gt;left[outline]&lt;/div&gt;
  &lt;div class="mod-preview-wrapper"&gt;
    &lt;ul class="menu"&gt;
      &lt;li&gt;&lt;!-- various menu items --&gt;&lt;/li&gt;
    &lt;/ul&gt;
  &lt;/div&gt;
&lt;/div&gt;</pre></div>
</td>
<td><img alt="Module chrome outline.png" src="https://docs.joomla.org/images/1/12/Module_chrome_outline.png" decoding="async" data-file-width="198" data-file-height="151" width="198" height="151">
</td></tr>
</tbody></table>

Note that the Module chrome doesn't necessarily change the appearance
all that much - this depends on the CSS used in the template. For
example, the '`none`' and '`horz`' chromes look very similar, although
the underlying HTML code is very different.

Other notes: The `horz` is just the `table` layout, wrapped in a
`table`, `tr`, and `td`.

Until Joomla! 3: The software controlling these is in the file
`/templates/system/html/modules.php`.

**Changes since Joomla! 4**

- The standard chromes `horz`, `rounded` and `xhtml` have been removed
  from core.
- The core module chromes are controlled by `JLayout` files in directory
  `/layouts/chromes/`.
