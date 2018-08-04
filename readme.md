tp50unit , unit test for thinkphp5.0, only test
==

test thinkphp5.0 app's logic by phpstorm 2018

**usage**
    
    composer require wsteel/php50unit

**require**
    
    "php": ">=7.0.0",
    "topthink/framework": "5.0.*"
    "phpunit/phpunit": "6.*"

**demo**

filename

    tests/demo/demoTest.php

content
```php

namespace tests\demo;

use wsteel\tp50unit\TestCase;

class demoTest extends TestCase
{

    public function testTrue()
    {
        $this->assertTrue(true);
    }

    public function testFalse()
    {
        $this->assertFalse(false, 'false');
    }


    public function testModel()
    {
        $e = \app\serverapi\model\Users::get(1)->toArray();
        $this->assertNotEmpty($e);
    }

    public function testM()
    {
        $user = model('users', 'serverapi\model');
        $e = $user->where('id', 1)->find()->toArray();
        $this->assertNotEmpty($e);
    }

    public function testDB()
    {
        $user = \think\Db::name('server_user');
        $e = $user->where('id', 1)->find();
        $this->assertNotEmpty($e);
    }

    public function testConfig()
    {
        $config = config('serverapi');
        $this->assertNotEmpty($config);
    }
}

```