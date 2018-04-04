# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Unauthenticated Stored Cross-Site Scripting (XSS) (ID: 7945)
  - [ ] Summary: Uses an extremely long comment to truncate the comment when inserted into a database, thus allowing you to input a XSS injection.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
	1. Go to wordpress forum
	2. Make a comment with the XSS code (must be larger than 64kilobytes).
	a. <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  ZZZZZZZZZ...[64 kb]..ZZZ'></a>
	3. Have it approved by admin.
	4. When you go to the forum with the comment, a pop up will happen (if that's what you 		made your code do).
  - [ ] Affected source code:
    - [Link 1](https://klikki.fi/adv/wordpress2.html)
1. wp_untrash_post_comments SQL Injection (ID: 8126)
  - [ ] Summary: SQL injection vulnerability in the wp_untrash_post_comments function in wp-includes/post.php in WordPress before 4.2.4 allows remote attackers to execute arbitrary SQL commands via a comment that is mishandled after retrieval from the trash. 
    - Vulnerability types: CVE: 2015-2213. SQL Injection. 
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code: https://core.trac.wordpress.org/changeset/33556/branches/4.2/src/wp-includes/post.php?contextall=1
    - [Link 1](https://wpvulndb.com/vulnerabilities/8126)
1. (Required) Authenticated Stored Cross-Site Scripting (XSS)(ID: 8111)
  - [ ] Summary: Allows user with posting capability to compromise website. The attacker would insert specially formatted HTML containing JavaScript on a WordPress page or post. Some special configurations may allow posting or editing page content for unauthenticated users. 
    - Vulnerability types: XSS, CVE: 2015-5622,5623
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
	1. Input any form of XSS code (such as <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>) into a page or post.
	2. XSS will execute when an administrator views the page.
  - [ ] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/8111)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

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
