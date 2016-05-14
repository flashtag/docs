# Making a Theme

The easiest thing to do would be to copy an existing theme, like the default `clean-creative` theme. To do this, just copy `resources/views/themes/clean-creative` to `resources/views/themes/my-new-theme`.

Then, in the Settings menu of the admin dashboard change the theme to your new theme.

# Installing a theme package

Installing a theme using the packagist name (e.g. `vendor/theme`):

```
php artisan flashtag:install-theme vendor/theme
```

# Making a theme package

## A) Starting From Scratch

To make your own theme from scratch id pretty simple.
### 1. Make a composer package

Add `theme.php`

```php
<?php

return [

    'name' => 'clean-creative',

    'version' => '0.0.1',

    'views' => __DIR__.'/views',

    'assets' => __DIR__.'/assets',

];

```

### 2. Create your views

| required blade views  | variables available
|-----------------------|---------------------
| home                  |
| posts.index           | Collection $posts
| posts.show            | Post $post
| posts.category        | Category $category, Collection $posts
| posts.tag             | Tag $tag, Collection $posts
| posts.author          | Author $author, Collection $posts
| pages.default-page    | Page $page

## B) Forking

Fork and edit the [example repo](https://github.com/flashtag-themes/clean-creative).

Make sure you edit `theme.php` ***and*** `composer.json`!

Make a packagist package out of it.
