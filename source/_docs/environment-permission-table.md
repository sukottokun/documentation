--- 
title: Environment Permission Table 
description: Learn how Pantheon directory tree permission in different connection mode in different environment. 
categories: [drupal, wordpress, sftp, git] 
tags: [code, platform] 
--- 
 
Tell about Confusion of permission 
 
## Table matrix of permission

<table>
	<thead>
		<tr>
			<th colspan="6">Directory Permission Matrix</th>
		</tr>
		<tr>
			<td colspan="3">Directory Paths</td>
			<td colspan="3">Environment's Name</td>
		</tr>
		<tr>
			<td rowspan="2">Container</td>
			<td rowspan="2">Drupal</td>
			<td rowspan="2">Wordpress</td>
			<td colspan="2">Dev &amp; Multi-Dev</td>
			<td>Test &amp; Live</td>
		</tr>
		<tr>
			<td>SFTP Mode</td>
			<td>Git Mode</td>
			<td>Only Git Mode</td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td rowspan="5">/src/[binding-id]/</td>
			<td>code/*</td>
			<td>code/*</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>code/sites/default/files<br>symlink to files/*</td>
			<td>code/wp-content/uploads/<br>symlink to files/*</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>files/*</td>
			<td>files/*</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>logs/*</td>
			<td>logs/*</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>...</td>
			<td>...</td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>   

