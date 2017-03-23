# vanilla
This is a personal repo for quickly creating new Drupal 8 websites on my local machine for development.<br>
The scripts use standard D8 composer installation process,
copies a set of files such as settings.php customised to my use,
and installs some modules I usually use using composer.<br>
It also adds the entry to the aliases.drushrc.php file assuming the user running
the script has access rights to the file.<br>
<br>
The 'newD8site' script attempts to copy a settings.local.php file into place. This
file is not included in git in order to protect database authentication details.
before using the scripts,<br>
 copy  'sites/example.settings.local.php' <br>
 to    'sites/newsite/settings.local.php' <br>
 and add the following immediately after the <?php<br>
<pre>  /**
   * Database settings:
   */
  
  $databases['default']['default'] = array (
    'database' => 'drupal8db',
    'username' => 'd8user',
    'password' => 'password',
    'prefix' => 'newsite_',
    'host' => 'localhost',
    'port' => '3306',
    'namespace' => 'Drupal\\Core\\Database\\Driver\\mysql',
    'driver' => 'mysql',
  );</pre><br>
 Modify the database name and authentication details to those you use.<br>
<br>
Similarly, the aliases entry has dummy database details.<br>
 edit scaffold/aliases.drush and enter real values.<br>
<br>
git is also initialised in the new site's directory and a gitignore created.<br>
The scripts are bash and use kdialog, so assume kde is installed.
