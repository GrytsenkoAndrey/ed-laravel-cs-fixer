# ed-laravel-cs-fixer
Setup PHP-CS-Fixer for Laravel Project

Whether you are working on a small project or a big project with multiple team members, then you need to follow proper coding standards to maintain code stability.

Laravel follows the PSR-2 coding standard and the PSR-4 autoloading standard. To maintain the same coding standard as PSR-2 for your project(s) there are multiple packages available that can help you fix your code to follow standards.

In this article, we will use PHP Coding Standards Fixer to setup it up on a Laravel project level.

The following are the steps:

## Step # 1

Go to your project root folder and run the following command:

```
composer require friendsofphp/php-cs-fixer --dev
```

## Step # 2

In your project root, create a new file named .php-cs-fixer.php and add the following code and then save it.

```
<?php

use PhpCsFixer\Config;
use PhpCsFixer\Finder;
$rules = [
    'array_syntax' => ['syntax' => 'short'],
    'binary_operator_spaces' => [
        'default' => 'single_space',
        'operators' => ['=>' => null]
    ],
    'blank_line_after_namespace' => true,
    'blank_line_after_opening_tag' => true,
    'blank_line_before_statement' => [
        'statements' => ['return']
    ],
    'single_space_around_construct' => true,
    'control_structure_braces' => true,
    'curly_braces_position' => true,
    'control_structure_continuation_position' => true,
    'declare_parentheses' => true,
    'statement_indentation' => true,
    'no_multiple_statements_per_line' => true,
    'cast_spaces' => true,
    'class_attributes_separation' => [
        'elements' => [
           'method' => 'one',
           'trait_import' => 'none'
        ]
    ],
    'class_definition' => true,
    'concat_space' => [
        'spacing' => 'one'
    ],
    'declare_equal_normalize' => true,
    'elseif' => true,
    'encoding' => true,
    'full_opening_tag' => true,
    'fully_qualified_strict_types' => true,
    'function_declaration' => true,
    'function_typehint_space' => true,
    'heredoc_to_nowdoc' => true,
    'include' => true,
    'increment_style' => ['style' => 'post'],
    'indentation_type' => true,
    'linebreak_after_opening_tag' => true,
    'line_ending' => true,
    'lowercase_cast' => true,
    'constant_case' => true,
    'lowercase_keywords' => true,
    'lowercase_static_reference' => true,    
    'magic_method_casing' => true,
    'magic_constant_casing' => true,
    'method_argument_space' => true,
    'native_function_casing' => true,
    'no_alias_functions' => true,
    'no_extra_blank_lines' => [
        'tokens' => [
            'extra',
            'throw',
            'use'
        ]
    ],
    'no_blank_lines_after_class_opening' => true,
    'no_blank_lines_after_phpdoc' => true,
    'no_closing_tag' => true,
    'no_empty_phpdoc' => true,
    'no_empty_statement' => true,
    'no_leading_import_slash' => true,
    'no_leading_namespace_whitespace' => true,
    'no_mixed_echo_print' => [
        'use' => 'echo'
    ],
    'no_multiline_whitespace_around_double_arrow' => true,
    'multiline_whitespace_before_semicolons' => [
        'strategy' => 'no_multi_line'
    ],
    'no_short_bool_cast' => true,
    'no_singleline_whitespace_before_semicolons' => true,
    'no_spaces_after_function_name' => true,
    'no_spaces_around_offset' => true,
    'no_spaces_inside_parenthesis' => true,
    'no_trailing_comma_in_singleline' => true,
    'no_trailing_whitespace' => true,
    'no_trailing_whitespace_in_comment' => true,
    'no_unneeded_control_parentheses' => true,
    'no_unreachable_default_argument_value' => true,
    'no_useless_return' => true,
    'no_whitespace_before_comma_in_array' => true,
    'no_whitespace_in_blank_line' => true,
    'normalize_index_brace' => true,
    'not_operator_with_successor_space' => false,
    'object_operator_without_whitespace' => true,
    'ordered_imports' => ['sort_algorithm' => 'alpha'],
    'phpdoc_indent' => true,
    'general_phpdoc_tag_rename' => true,
    'phpdoc_inline_tag_normalizer' => true,
    'phpdoc_tag_type' => true,
    'phpdoc_no_access' => true,
    'phpdoc_no_package' => true,
    'phpdoc_no_useless_inheritdoc' => true,
    'phpdoc_scalar' => true,
    'phpdoc_single_line_var_spacing' => true,
    'phpdoc_summary' => true,
    'phpdoc_to_comment' => true,
    'phpdoc_trim' => true,
    'phpdoc_types' => true,
    'phpdoc_var_without_name' => true,
    'psr_autoloading' => true,
    'self_accessor' => true,
    'short_scalar_cast' => true,
    'simplified_null_return' => false,
    'single_blank_line_at_eof' => true,
    'single_blank_line_before_namespace' => true,
    'single_class_element_per_statement' => true,
    'single_import_per_statement' => true,
    'single_line_after_imports' => true,
    'single_line_comment_style' => [
        'comment_types' => ['hash']
    ],
    'single_quote' => true,
    'space_after_semicolon' => true,
    'standardize_not_equals' => true,
    'switch_case_semicolon_to_colon' => true,
    'switch_case_space' => true,
    'ternary_operator_spaces' => true,
    'trailing_comma_in_multiline' => true,
    'trim_array_spaces' => true,
    'unary_operator_spaces' => true,
    'visibility_required' => [
        'elements' => ['method', 'property']
    ],
    'whitespace_after_comma_in_array' => true,
    'no_unused_imports' => true,
];


$finder = Finder::create()
    ->in([
        __DIR__ . '/app',
        __DIR__ . '/config',
        __DIR__ . '/database',
        __DIR__ . '/resources',
        __DIR__ . '/routes',
        __DIR__ . '/tests',
    ])
    ->name('*.php')
    ->notName('*.blade.php')
    ->ignoreDotFiles(true)
    ->ignoreVCS(true);

$config = new Config();
return $config->setFinder($finder)
    ->setRules($rules)
    ->setRiskyAllowed(true)
    ->setUsingCache(true);
```

This file contains local configuration that will be used instead of project configurations. It will let you configure rules, the files and directories that need to be analysed.

Feel free to change the above file to suit your needs.

## Step # 3

Open composer.json file and add the following lines to the script section:

```
"sniff": [
     "./vendor/bin/php-cs-fixer fix -vvv --dry-run --show-progress=dots"
],
"lint": [
    "./vendor/bin/php-cs-fixer fix -vvv --show-progress=dots"
],
```

With this we have added two scripts that we can run with composer command:

- composer sniff
  This command is used for dry-run to show you all the files that needs to be fixed without fixing them.

- composer lint
  This command will try to auto fix your code and will show you the summary at the end.

Following are some useful links:

- [PHP-CS-Fixer Package](https://github.com/FriendsOfPHP/PHP-CS-Fixer)
- [PHP-CS-Fixer Documentation](https://github.com/PHP-CS-Fixer/PHP-CS-Fixer/blob/master/doc/usage.rst)
- [PHP-CS-Fixer Configurations](https://mlocati.github.io/php-cs-fixer-configurator/#version:3.16)

If you want to install PHP Coding Standards Fixer on your favourite editor then following dedicated plugins are available:

- [Atom](https://github.com/Glavin001/atom-beautify)
- [NetBeans](https://plugins.netbeans.apache.org/catalogue/?id=36)
- [PhpStorm](https://medium.com/@valeryan/how-to-configure-phpstorm-to-use-php-cs-fixer-1844991e521f)
- [Sublime Text](https://github.com/benmatselby/sublime-phpcs)
- [Vim](https://github.com/stephpy/vim-php-cs-fixer)
- [VS Code](https://github.com/junstyle/vscode-php-cs-fixer)

# How to configure PHPStorm to use PHP-CS-Fixer

So we start our journey with some prerequisites:

- PHPStorm installed
- Composer Installed and added to your path
- PHP-CS-Fixer installed via Composer

Decision time! Because I am on windows I found that passing any kind of complex configuration to the PHP-CS-Fixer was impossible because it would require passing valid Json through cmd.exe and cmd.exe strips out all the double quotes from the Json. Also, it gets pretty ridiculous to pass a massive set of rules configuration to PHP-CS-Fixer so the configuration route provides a much better way to get this done. However, you can pass the full configuration to the tool using ```--rules='{"rule_name": "value", ...}'```

My recommendation is to use the config file though. Also, if you just want rules for a specific project you can drop the php_cs.dist file into the root of the project and skip adding the rules or config argument to this and PHP-CS-Fixer will grab it automagically.

Now you can set up the configuration for PHP-CS-Fixer. You can grab an example configuration from the project repo and modify it to match your needs. The documentation for all the rules is pretty extensive in their README, so check that out. Once you have that set note where your file is located for later steps.

Open PHPStorm, go to the File menu and find Settings (maybe Preferences on OSX). The dialog that opens gives you access to all the many settings of PHPStorm. Look near the bottom of the list of settings for Tools and then External Tools or just Type External Tools in the search bar. When you select External Tools you will mostly likely see an empty list with some controls at the top. Hit the green plus icon.

You should see a blank dialog for adding an external tool like this:
![image](https://github.com/GrytsenkoAndrey/ed-laravel-cs-fixer/assets/63291871/9268e894-c307-4d27-9248-39d438e65c8d)

Let’s set up this tool now. The name and description are arbitrary. I usually go for something like “Fix my stupid code Tool” but it's up to you. Be creative! Most of the checked boxes are fine but once you have this working the way you want, you might want to come back and uncheck the Open Console option. Leave it, for now, we will need to see the output.

## Program Field

Next, we need to populate the Program field. This will need to point to the .phar or .bat for PHP-CS-Fixer depending on your platform. To get the correct value you can use which on *nix or where.exe on Windows.

OSX or Linux you will get something like this:

```
$ which php-cs-fixer
$ /home/username/.composer/vendor/bin/php-cs-fixer
```

Windows:

```
$ where.exe php-cs-fixer
$ C:\Users\user\AppData\Roaming\Composer\vendor\bin\php-cs-fixer
$ C:\Users\user\AppData\Roaming\Composer\vendor\bin\php-cs-fixer.bat
```

Copy the path into the program field and be sure to include the .bat extension if you are on windows.

## Parameters

Now for Parameters. Parameters are appended after the program in the grand scheme of things so we start by adding fix --verbose then the rules or config argument --config=path/to/php_cs.dist or --rules=@PSR2 and then a few PHPStorm macros to get the file path and name "$FileDir$/$FileName$”. Additionally, it may be a good idea to add--path-mode=intersection as well to prevent a problem where you pass a filename from the tool that has been excluded by your config. All together that might look like this:

```
fix --verbose --config=C:\path\to\php_cs.dist --path-mode=intersection "$FileDir$/$FileName$"
```

## Working Directory

The final field on the dialog is for the working directory and you can get that pretty easily from another PHPStorm macro $ProjectFileDir$. With all that in place your Tool settings should now look like this:

![image](https://github.com/GrytsenkoAndrey/ed-laravel-cs-fixer/assets/63291871/043de5b7-253f-409d-b055-7b4bbd1fdd33)

Hit OK, and you now have the external tool configured. Don’t close settings just yet though. To make this tool super useful we are going to travel up the settings list to Keymap.

## Keymap

Click or search for Keymap in settings. Then in the keymap window find External Tools and then again External Tools and Then whatever you named your external tool we just configured. Double-click your external tool or the green pencil at the top and select Add Keyboard Shortcut from the list. Then type a key combo (I use Alt+F) and hit OK, and then, hit OK again on settings.

## Testing it out

Now click into an open PHP file, or open one from your project. Make sure the cursor is in the file and then hit your key combo. You will see the console open and you should get an output something like this:

![image](https://github.com/GrytsenkoAndrey/ed-laravel-cs-fixer/assets/63291871/0f466114-0637-4708-a8d6-f5507ca19882)

If you get some errors you will most probably have something wrong with the Parameters field or your config is not right. If everything goes well, you can open the external tool settings again and uncheck open console, unless you just like having it open.

Now go forth and program without worrying about all that formatting. You can clean it all up later with the click of a few buttons.
