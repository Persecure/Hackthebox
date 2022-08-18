<!-- wp:paragraph -->
<p><a href="https://app.hackthebox.com/machines/Active">https://app.hackthebox.com/machines/Active</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Windows machines that run kerberos or ldap can be enumerated with smbmap</li><li>Enter read only files with smbclient to recon </li><li>Group policy files contains usernames and password hashes</li><li>Use gpp-decrypt or Group Policy Preferences (Group Policy Preferences) to decrypt hashes</li><li>Use Impacket's GetUserSPNs.py script to get a list of service usernames mapped to regular user accounts</li><li>Hashcat (13100) Kerberos 5 can be used to decrypt the hash to get the Administrator's password</li></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"luminous-vivid-amber","fontSize":"small"} -->
<p class="has-text-align-center has-luminous-vivid-amber-background-color has-background has-small-font-size"><strong>Enumeration</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Run nmap scan to find for open ports.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3485,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-497.png?w=1024" alt="" class="wp-image-3485"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run smbmap to find for shares.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3486,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-498.png?w=1024" alt="" class="wp-image-3486"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3487,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-499.png?w=914" alt="" class="wp-image-3487"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Found a xml file </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3488,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-500.png?w=1024" alt="" class="wp-image-3488"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It contains a username and password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3492,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-502.png?w=1024" alt="" class="wp-image-3492"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use gpp-decrypt to crack the password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3493,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-503.png?w=1024" alt="" class="wp-image-3493"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>With the newly found credentials we can use smbmap to gain access with the new user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3494,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-504.png?w=1024" alt="" class="wp-image-3494"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First flag can be found in the desktop on SVC_TGS folder.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3496,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-505.png?w=933" alt="" class="wp-image-3496"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3498,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-506.png?w=433" alt="" class="wp-image-3498"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use Impacket's GetUserSPNs.py script to get a list of service usernames mapped to regular user accounts. Which also gets a ticket that can be cracked.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3499,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-507.png?w=1024" alt="" class="wp-image-3499"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>It also gives me the ticket, which I can try to brute force decrypt to get the user’s password:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3501,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-508.png?w=900" alt="" class="wp-image-3501"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use hashcat to crack the password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3503,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-509.png?w=988" alt="" class="wp-image-3503"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>password: Ticketmaster1968</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3505,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-510.png?w=1024" alt="" class="wp-image-3505"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Gain access to the Administrator account via smbclient.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3506,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-511.png?w=1024" alt="" class="wp-image-3506"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Final flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3507,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-512.png?w=1024" alt="" class="wp-image-3507"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3509,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-513.png?w=480" alt="" class="wp-image-3509"/></figure>
<!-- /wp:image -->
