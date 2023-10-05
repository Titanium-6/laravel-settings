# Laravel Settings #

A simple way to manage your settings in Laravel without the complexity of packages like `spatie/laravel-settings`.

> Breaking Changes in Laravel Settings v2

## Install Options ##
### Option 1: Add directly to your composer.json ###
```
"require": {
    "sgtcoder/laravel-settings": "2.*"
}

"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/sgtcoder/laravel-settings"
    }
]
```

### Option 2: Fork it and add to your composer.json ###
```
"require": {
    "sgtcoder/laravel-settings": "dev-master"
}

"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/<workspace>/laravel-settings"
    }
]
```


### Then Run ###
```
composer update
```

## Publish Migration ##
```
php artisan vendor:publish --provider="SgtCoder\LaravelSettings\LaravelSettingsServiceProvider" --tag="migrations"

php artisan migrate
```

## Usage ##
### Get Single Setting From General or Default Group ###
```
settings()->get('setting_name');
settings('general')->get('setting_name');
```

### Get Single Setting From General or Default Group with Media using Plank and MediaService ###
```
settings()->get('setting_name', $media = true);
settings('general')->get('setting_name', $media = true);
```

### Get All Settings from General or Default Group
```
settings()->get();
settings('general')->get();
```

### Get All Settings Grouped with Model Collection from General or Default Group ###
```
settings()->grouped()->get();
settings()->grouped('general')->get();
settings()->grouped('general')->get('setting_name');
```

### Set Settings for General or Default Group
```
settings()->set($settings);
settings('general')->set($settings);
```

### Set Single Setting for General or Default Group ###
```
settings()->setAttribute('setting_name', 'setting_value');
settings('general')->setAttribute('setting_name', 'setting_value');
```

### Replace Settings for General or Default Group (And Deletes Nulls) ###
```
settings()->replace($settings);
settings('general')->replace($settings);
```