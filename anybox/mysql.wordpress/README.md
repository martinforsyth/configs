#
# Moving a site or multisite
#
# ref https://codex.wordpress.org/Moving_WordPress
#
# Also, manually review all the wp_x_options tables and look for four fields and edit them as needed:
#
# home
# siteurl
# upload_path
# upload_url_path
#
# Sample SQL to find entries to change ...
#
# Default is localhost
#
# Also see https://www.siteground.com/kb/change-domain-wordpress-multisite/ 
# where it says these tables need editing ...
#
# wp_options: lines named “siteurl” and “home”
# wp_site
# wp_sitemeta: the entry named “siteurl”
# wp_blogs: any entries in the “domains” column that have the old domain name
# wp_#_options: As every sub-site will have sets of tables that correspond to the blog_id in the wp_blogs table. You need to navigate to the wp_#_options table, where # corresponds to the blog_id, and update the “siteurl” and “home” values in the table.
#

SELECT option_name, option_value FROM wordpress.wp_2_options WHERE option_value LIKE '%192%';

SELECT * FROM wordpress.wp_site ;
SELECT * FROM wordpress.wp_sitemeta ;
SELECT * FROM wordpress.wp_blogs ;
