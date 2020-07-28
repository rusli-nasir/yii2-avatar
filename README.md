fork from daimakuai/yii2-avatar

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist rusli-nasir/yii2-avatar "dev-master"
```

or add

```
"rusli-nasir/yii2-avatar": "dev-master"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php

//在当前控制器的actions中添加如下配置
public function actions()
{
    return [
        'crop'=>[
            'class' => 'dxapp\avatar\CropAction',
            'config'=>[
                'bigImageWidth' => '200',     
                'bigImageHeight' => '200',    
                'middleImageWidth'=> '100',   
                'middleImageHeight'=> '100',  
                'smallImageWidth' => '50',    
                'smallImageHeight' => '50',   
                
                //Avatar upload directory (Note: "/" cannot be added before the directory)
                'uploadPath' => 'uploads/avatar',
            ]
        ]
    ]; 
    
}
 
//Calling method, imageUrl is the default image address
<?= \daimakuai\avatar\AvatarWidget::widget(['imageUrl'=>'/statics/images/avatar/avatar.jpg']); ?>
```
在From里可以单独使用
```php

放到Form里

<?= $form->field($model, 'avatar')->widget(\daimakuai\avatar\AvatarViewWidget::className()) ?>


放到Form外
<?php $obj = new \daimakuai\avatar\AvatarUploadWidget(['imageUrl'=>'/statics/images/avatar/avatar.jpg']);echo $obj->setFooter(); ?>

```
