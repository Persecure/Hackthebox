<!-- wp:paragraph -->
<p>https://app.hackthebox.com/machines/Nibbles</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Directory enumeration revels hidden information</li><li>Login page credentials are simple</li><li>RCE can be done from plugins</li><li>Privilege execution can be achieved by editing a monitor script</li></ul>
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

<!-- wp:image {"id":3576,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-538.png?w=1024" alt="" class="wp-image-3576"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80 </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3578,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-539.png?w=492" alt="" class="wp-image-3578"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>View source gives a clue.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3580,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-540.png?w=496" alt="" class="wp-image-3580"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3581,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-541.png?w=1024" alt="" class="wp-image-3581"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Main site does not bring in much directories, tried it with the nibbleblog sub directory.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3586,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-544.png?w=1024" alt="" class="wp-image-3586"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/contents/</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3583,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-542.png?w=561" alt="" class="wp-image-3583"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>/content/private/users.xml</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3584,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-543.png?w=639" alt="" class="wp-image-3584"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Readme indicates the version of the interface.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3587,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-545.png?w=642" alt="" class="wp-image-3587"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>After sometime bruteforcing the login page , I tried the name of the box and access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3589,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-546.png?w=558" alt="" class="wp-image-3589"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3591,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-547.png?w=1024" alt="" class="wp-image-3591"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Found an exploit without the use of metasploit</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3592,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-548.png?w=1024" alt="" class="wp-image-3592"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Head to the plugins My image page and upload a php reverse shell.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3594,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-549.png?w=1024" alt="" class="wp-image-3594"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Start a nc listener and activate the reverse shell script.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3595,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-550.png?w=1024" alt="" class="wp-image-3595"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>User access gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3597,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-551.png?w=888" alt="" class="wp-image-3597"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>User flag found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3598,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-552.png?w=450" alt="" class="wp-image-3598"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Check for sudo permisions.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3600,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-553.png?w=1024" alt="" class="wp-image-3600"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3602,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-554.png?w=1024" alt="" class="wp-image-3602"/><figcaption class="wp-element-caption">Looks like some kind of server health monitoring script.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's echo a shell in monitor.sh and root access is gained.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3606,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-556.png?w=506" alt="" class="wp-image-3606"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root flag is found</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3607,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-557.png?w=444" alt="" class="wp-image-3607"/></figure>
<!-- /wp:image -->
