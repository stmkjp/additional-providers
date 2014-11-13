additional-providers
====================

hybridauth providers for Kakao and Naver

PHP 를 사용해 웹싸이트를 만들때, 카카오톡 로그인 또는 네이버 로그인 구현하는 OAuth2 클라이언트. hybridauth 패키지를 설치한 뒤에, 사용할 수 있습니다.

How to use
----------

Just copy the files into `{project-root}/vendor/hybridauth/hybridauth/hybridauth/Hybrid/Providers`

Then, create a configuration file in `{project-root}/app/config` folder like

```php
return array(

    'base_url' => 'http://tamedbitches.app:8000/social/auth',

    'providers' => array (

        'Facebook' => array (
            'enabled' => TRUE,
            'keys'    => array ( 'id' => '81084046564????', 'secret' => 'fdd5d7f19d67bd220c855940da56????' ),
            "scope"   => "email",
        ),

        "Kakao" => array (
            "enabled" => TRUE,
            "keys"    => array ( "id" => "53a30c18096a18bda29162111208????", "secret" => "????" ),
        ),

        'Naver' => array (
            'enabled' => TRUE,
            'keys'    => array ( 'id' => 'ILH9AXW0mfxQZf_U????', 'secret' => '????' )
        ),
    ),

);
```

To register IoC binding, add the following snippet into `{project-root}/app/start/global.php`

```
App::bind('Hybrid_Auth', function() {
    return new Hybrid_Auth(app_path().'/config/hybridauth.php');
});
```

* I assumed you're using Laravel 4.x PHP framework. But, the hybridauth
package itself isn't necessarily dependent on any specific PHP frameworks.

Buy me a beer if you use my code
--------------------------------

If you’re also interested in practicing nerdism in Seoul area, perhaps we can get together
and have a chance to know each other better or just for the sake of munching dried squid. :beer: Happy coding!

References
----------

hybridauth 패키지 (http://hybridauth.sourceforge.net/)

카카오 계정으로 로그인 (https://developers.kakao.com/docs/restapi) 

네이버 아이디로 로그인 (http://developer.naver.com/wiki/pages/NaverLogin)

Contact me
----------

Chuck JS. Oh

http://facebook.com/chuckoh

<jinseokoh@hotmail.com>
