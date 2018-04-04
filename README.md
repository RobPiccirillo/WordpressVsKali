# Project 7 - WordPress Pentesting

Time spent: **4** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Title: Unauthenticated Stored Cross-Site Scripting (XSS) (ID: 7945)
  - [ ] Summary: Uses an extremely long comment to truncate the comment when inserted into a database, thus allowing you to input a XSS injection.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: 
  
  <div style='position:relative;padding-bottom:54%'><iframe src='https://gfycat.com/ifr/GargantuanBelatedHedgehog' frameborder='0' scrolling='no' width='100%' height='100%' style='position:absolute;top:0;left:0' allowfullscreen></iframe></div>
  
  
  - [ ] Steps to recreate: 
  
	1. Go to wordpress forum
	
	2. Make a comment with the XSS code (must be larger than 64kilobytes).
	
	a. such as ex:(<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  ZZZZZZZZZ...[64 kb]..ZZZ'></a>)
	
	3. Have it approved by admin.
	
	4. When you go to the forum with the comment, a pop up will happen (if that's what you 		made your code do).
	
  - [ ] Affected source code:
    - [Link 1](https://klikki.fi/adv/wordpress2.html)
    
2. Title: Authenticated Cross-Site scripting (XSS) in update-core.php (ID: 8716)
  - [ ] Summary: Multiple cross-site scripting (XSS) vulnerabilities in wp-admin/update-core.php in WordPress before 4.7.1 allow remote attackers to inject arbitrary web script or HTML via both the name and header of a plugin.
    - Vulnerability types: XSS, CVE: 2017-5488
    - Tested in version: 4.2
    - Fixed in version: 4.7.1
  - [ ] GIF Walkthrough: 
  
<div style='position:relative;padding-bottom:54%'><iframe src='https://gfycat.com/ifr/ScornfulShimmeringHornbill' frameborder='0' scrolling='no' width='100%' height='100%' style='position:absolute;top:0;left:0' allowfullscreen></iframe></div>  


  - [ ] Steps to recreate:
  
  	1. Edit any plugins name to be some form of script (contained within script tags)
	
	2. Navigate to to wp-admin/update-core.php
	
  - [ ] Affected source code: https://core.trac.wordpress.org/browser/trunk/src/wp-includes/shortcodes.php
    - [Link 1](https://wpvulndb.com/vulnerabilities/8716)
    
3. Title: Authenticated Stored Cross-Site Scripting (XSS)(ID: 8111)
  - [ ] Summary: Allows user with posting capability to compromise website. The attacker would insert specially formatted HTML containing JavaScript on a WordPress page or post. Some special configurations may allow posting or editing page content for unauthenticated users. 
    - Vulnerability types: XSS, CVE: 2015-5622,5623
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  
 <div style='position:relative;padding-bottom:54%'><iframe src='https://gfycat.com/ifr/PointlessThornyBobwhite' frameborder='0' scrolling='no' width='100%' height='100%' style='position:absolute;top:0;left:0' allowfullscreen></iframe></div>
  
  
  - [ ] Steps to recreate:
	1. Create new page/pos
	
	2. Using HTML editor, input any form of XSS code (such as <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>) into the page/post.
	
	3. XSS will execute when an administrator views the page.
	
  - [ ] Affected source code: https://core.trac.wordpress.org/changeset/33359
    - [Link 1](https://wpvulndb.com/vulnerabilities/8111)


## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
