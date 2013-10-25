---
layout: post
title:  "Length of Last Word"
date:   2013-10-24 19:38:34
categories: LeetCode
---

<h1>Question</h1>
<p>
	Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word in the string. </br>
	If the last word does not exist, return 0.</br>
	Note: A word is defined as a character sequence consists of non-space characters only.</br>
	For example,</br>
	Given s = "Hello World",</br>
	return 5.
</p>

<h1>Analysis</h1>
<p>
	It is pretty straightforward that to scan the string once with O(n) running time. While scanning, keep record of the length of the last word. However, there may be multiple spaces at the end of the string, then an extra vairable need to be used to store the length of the word before the spaces. The previousResult in the following code should only be updated when the currentResult is not 0.
</p>

<h1>Result</h1>
<p>
	<script src="https://gist.github.com/myhgew/6652f4b50ade9ccc0556.js"></script>
</p>

<div id="reference">
	<h1>Reference</h1>
	<p>
		<a href='http://fisherlei.blogspot.com/2012/12/leetcode-length-of-last-word.html'>Length of Last Word</a>
	</p>
</div>
