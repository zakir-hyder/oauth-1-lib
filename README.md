OAuth 1 Lib
=============

This basically classes from http://oauth.googlecode.com/svn/code/php/OAuth.php. I followed steps from http://stackoverflow.com/questions/18831030/use-oauth-1-class-in-symfony2 

1) Add namespace OAuth; at the beginning of every OAuth class.

2) Add a backslash to the Exception class (or add use Exception;):

    class OAuthException extends \Exception

3) Avoid underscores in class names (Laravel-Oauth2 Issue in Laravel 4 , Underscores in Namespaces and Class Names):

    abstract class OAuthSignatureMethodRSASHA1 extends OAuthSignatureMethod

    class OAuthSignatureMethodPLAINTEXT extends OAuthSignatureMethod

    class OAuthSignatureMethodHMACSHA1 extends OAuthSignatureMethod

4) Fix the array_map call in OAuthUtil:

    return array_map(array('OAuth\OAuthUtil', 'urlencode_rfc3986'), $input);
