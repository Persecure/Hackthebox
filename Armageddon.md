<!-- wp:paragraph -->
<p><a href="https://app.hackthebox.com/machines/Armageddon" target="_blank" rel="noreferrer noopener">https://app.hackthebox.com/machines/Armageddon</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-purple","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-purple-background-color has-background has-small-font-size">Review</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Find service version through enumeration</li><li>Metasploit exploit will give a web shell</li><li>Databases credentials are stored openly</li><li>Use mysqldump to dump password hashes</li><li>Cracked hashes gives password for SSH login</li><li>Able to run snap install without root</li><li>Utilize dirty sock exploit to create an account and switch to root user without password</li></ul>
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

<!-- wp:image {"id":3658,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-567.png?w=874" alt="" class="wp-image-3658"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Port 80 brings us to some type of login page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3661,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-569.png?w=950" alt="" class="wp-image-3661"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Run a gobuster scan to find for hidden directories. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3664,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-571.png?w=1024" alt="" class="wp-image-3664"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ReadME.txt tells us it runs a Drupal source content management platform</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3659,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-568.png?w=725" alt="" class="wp-image-3659"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>In the profiles folders there are files that contain the Drupal version.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3663,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-570.png?w=646" alt="" class="wp-image-3663"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Use searchsploit to find for known exploits.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3666,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-572.png?w=819" alt="" class="wp-image-3666"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>**There was an issue running the ruby script on my system so I decided to use metasploit instead.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3667,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-573.png?w=1024" alt="" class="wp-image-3667"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3669,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-574.png?w=855" alt="" class="wp-image-3669"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"vivid-cyan-blue","fontSize":"small"} -->
<p class="has-text-align-center has-vivid-cyan-blue-background-color has-background has-small-font-size"><strong>Foothold</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Once the shell is gained , a user name is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3672,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-576.png?w=598" alt="" class="wp-image-3672"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Enumerating the folders , we can find some database credentials in /var/www/html/sites/default/settings.php</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3670,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-575.png?w=661" alt="" class="wp-image-3670"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's use mysqldump to dump everything.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3674,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-577.png?w=713" alt="" class="wp-image-3674"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3675,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-578.png?w=1024" alt="" class="wp-image-3675"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Let's crack the hash with John the ripper.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3677,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-579.png?w=730" alt="" class="wp-image-3677"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Login to the user via ssh.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3679,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-580.png?w=1024" alt="" class="wp-image-3679"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>First flag is found</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3680,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-581.png?w=593" alt="" class="wp-image-3680"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We are able to run the snap install with sudo and no password.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3682,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-582.png?w=1024" alt="" class="wp-image-3682"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Searching GTFOBins we get the following.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3685,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-584.png?w=879" alt="" class="wp-image-3685"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>We can also use a faster approach with dirtysock <a href="https://github.com/initstring/dirty_sock/blob/master/dirty_sockv2.py" data-type="URL" data-id="https://github.com/initstring/dirty_sock/blob/master/dirty_sockv2.py" target="_blank" rel="noreferrer noopener">here</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In the script we can use this payload.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3684,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-583.png?w=594" alt="" class="wp-image-3684"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center","backgroundColor":"black","textColor":"white","fontSize":"small"} -->
<p class="has-text-align-center has-white-color has-black-background-color has-text-color has-background has-small-font-size"><strong>Privilege escalation</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Run the following commands in python.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3687,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-585.png?w=658" alt="" class="wp-image-3687"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3688,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-586.png?w=843" alt="" class="wp-image-3688"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Once dirty sock is installed it creates a user call dirty sock with the same password.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>With this installed we are able to switch to the root user.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3690,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-587.png?w=1024" alt="" class="wp-image-3690"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Root flag is found.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3691,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://persecure.files.wordpress.com/2022/08/image-588.png?w=609" alt="" class="wp-image-3691"/></figure>
<!-- /wp:image -->
