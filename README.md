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
    'magic_method_casing' => true…
    ```
