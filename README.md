<h1 align="center">Arrays Component</h1>

<p align="center">
<a href="https://github.com/atomastic/arrays/releases"><img alt="Version" src="https://img.shields.io/github/release/atomastic/arrays.svg?label=version&color=green"></a> <a href="https://github.com/atomastic/arrays"><img src="https://img.shields.io/badge/license-MIT-blue.svg?color=green" alt="License"></a> <a href="https://github.com/atomastic/arrays"><img src="https://img.shields.io/github/downloads/atomastic/arrays/total.svg?color=green" alt="Total downloads"></a> <img src="https://github.com/atomastic/arrays/workflows/Static%20Analysis/badge.svg?branch=dev"> <img src="https://github.com/atomastic/arrays/workflows/Tests/badge.svg">
  <a href="https://app.codacy.com/gh/atomastic/arrays?utm_source=github.com&utm_medium=referral&utm_content=atomastic/arrays&utm_campaign=Badge_Grade_Dashboard"><img src="https://api.codacy.com/project/badge/Grade/72b4dc84c20145e1b77dc0004a3c8e3d"></a> <a href="https://codeclimate.com/github/atomastic/arrays/maintainability"><img src="https://api.codeclimate.com/v1/badges/a4c673a4640a3863a9a4/maintainability" /></a><a href="https://app.fossa.com/projects/git%2Bgithub.com%2Fatomastic%2Farrays?ref=badge_shield" alt="FOSSA Status"><img src="https://app.fossa.com/api/projects/git%2Bgithub.com%2Fatomastic%2Farrays.svg?type=shield"/></a>
</p>

<br>

* [Installation](#installation)
* [Usage](#usage)
* [Methods](#methods)
* [Tests](#tests)
* [License](#license)

### Installation

#### With [Composer](https://getcomposer.org)

```
composer require atomastic/arrays
```

### Usage

```php
use Atomastic\Arrays\Arrays;

// Using public method __construct()
$arrays = new Arrays();

// Using public static method create()
$arrays = Arrays::create();

// Using global helper function arrays()
$arrays = arrays();
```

### Methods

| Method | Description |
|---|---|
| <a href="#arrays_append">`append()`</a> | Push an item into the end of an array. |
| <a href="#arrays_all">`all()`</a> | Get all items from stored array. |
| <a href="#arrays_count">`count()`</a> | Return the number of items in a given key. |
| <a href="#arrays_create">`create()`</a> | Create a new arrayable object from the given elements. Initializes a Arrays object and assigns $items the supplied values. |
| <a href="#arrays_chunk">`chunk()`</a> | Create a chunked version of current array. |
| <a href="#arrays_combine">`combine()`</a> | Create an array using the current array as keys and the other array as values. |
| <a href="#arrays_divide">`divide()`</a> | Divide an array into two arrays. One with keys and the other with values. |
| <a href="#arrays_dot">`dot()`</a> | Flatten a multi-dimensional associative array with dots. |
| <a href="#arrays_delete">`delete()`</a> | Deletes an array value using "dot notation".|
| <a href="#arrays_flush">`flush()`</a> | Flush all values from the array. |
| <a href="#arrays_first">`first()`</a> | Get the first value from the current array. |
| <a href="#arrays_firstKey">`firstKey()`</a> | Get the first key from the current array. |
| <a href="#arrays_get">`get()`</a> | Get an item from an array using "dot" notation. |
| <a href="#arrays_has">`has()`</a> | Checks if the given dot-notated key exists in the array. |
| <a href="#arrays_prepend">`prepend()`</a> | Push an item into the beginning of an array. |
| <a href="#arrays_pull">`pull()`</a> | Get a value from the array, and remove it. |
| <a href="#arrays_last">`last()`</a> | Get the last value from the current array. |
| <a href="#arrays_lastKey">`lastKey()`</a> | Get the last key from the current array. |
| <a href="#arrays_isEqual">`isEqual()`</a> | Check if the current array is equal to the given `$array` or not. |
| <a href="#arrays_isAssoc">`isAssoc()`</a> | Determines if an array is associative. |
| <a href="#arrays_toArray">`toArray()`</a> | Get all items from stored array and convert them to array. |
| <a href="#arrays_toJson">`toJson()`</a> | Convert the current array to JSON. |
| <a href="#arrays_toQuery">`toQuery()`</a> | Convert the current array into a query string. |
| <a href="#arrays_toString">`toString()`</a> | Convert the current array to string recursively implodes an array with optional key inclusion. |
| <a href="#arrays_sortBySubKey">`sortBySubKey()`</a> | Sorts a associative array by a certain field. |
| <a href="#arrays_set">`set()`</a> | Set an array item to a given value using "dot" notation. If no key is given to the method, the entire array will be replaced. |
| <a href="#arrays_undot">`undot()`</a> | Expands a dot notation array into a full multi-dimensional array. |


#### Methods Details


##### <a name="arrays_append"></a> Method: `append()`

```php
/**
 * Push an item into the end of an array.
 *
 * @param mixed $value The new item to append
 */
function append($value = null): self
```

**Examples**

```php
$arrays = Arrays::create([
                        'movies' => [
                           'the_thin_red_line' => [
                               'title' => 'The Thin Red Line',
                               'directed_by' => 'Terrence Malick',
                               'produced_by' => 'Robert Michael, Geisler Grant Hill, John Roberdeau',
                               'decription' => 'Adaptation of James Jones autobiographical 1962 novel, focusing on the conflict at Guadalcanal during the second World War.'
                           ],
                           'bad_times_at_the_el_royale' => [
                               'title' => 'Bad Times at the El Royale',
                               'directed_by' => 'Drew Goddard',
                               'produced_by' => 'Drew Goddard, Steve Asbell',
                               'decription' => 'Early 1970s. Four strangers check in at the El Royale Hotel. The hotel is deserted, staffed by a single desk clerk. Some of the new guests reasons for being there are less than innocent and some are not who they appear to be.'
                           ]
                        ]
                    ])->append(['tv-series']);
```


##### <a name="arrays_all"></a> Method: `all()`

```php
/**
 *  Get all items from stored array.
 */
public function all(): array
```

**Examples**

```php
$arrays = Arrays::create([
                        'movies' => [
                           'the_thin_red_line' => [
                               'title' => 'The Thin Red Line',
                               'directed_by' => 'Terrence Malick',
                               'produced_by' => 'Robert Michael, Geisler Grant Hill, John Roberdeau',
                               'decription' => 'Adaptation of James Jones autobiographical 1962 novel, focusing on the conflict at Guadalcanal during the second World War.'
                           ],
                           'bad_times_at_the_el_royale' => [
                               'title' => 'Bad Times at the El Royale',
                               'directed_by' => 'Drew Goddard',
                               'produced_by' => 'Drew Goddard, Steve Asbell',
                               'decription' => 'Early 1970s. Four strangers check in at the El Royale Hotel. The hotel is deserted, staffed by a single desk clerk. Some of the new guests reasons for being there are less than innocent and some are not who they appear to be.'
                           ]
                        ]
                    ]);

foreach ($arrays->all() as $key => $value) {
    // code...
}
```


##### <a name="arrays_count"></a> Method: `count()`

```php
/**
 * Return the number of items in a given key.
 *
 * @param  int|string|null $key
 */
public function count($key = null): int
```

**Examples**

```php
$arrays = Arrays::create([
                        'movies' => [
                           'the_thin_red_line' => [
                               'title' => 'The Thin Red Line',
                               'directed_by' => 'Terrence Malick',
                               'produced_by' => 'Robert Michael, Geisler Grant Hill, John Roberdeau',
                               'decription' => 'Adaptation of James Jones autobiographical 1962 novel, focusing on the conflict at Guadalcanal during the second World War.'
                           ],
                           'bad_times_at_the_el_royale' => [
                               'title' => 'Bad Times at the El Royale',
                               'directed_by' => 'Drew Goddard',
                               'produced_by' => 'Drew Goddard, Steve Asbell',
                               'decription' => 'Early 1970s. Four strangers check in at the El Royale Hotel. The hotel is deserted, staffed by a single desk clerk. Some of the new guests reasons for being there are less than innocent and some are not who they appear to be.'
                           ]
                        ]
                    ]);

$total = $arrays->count();
```

##### <a name="arrays_create"></a> Method: `create()`

```php
/**
 * Create a new arrayable object from the given elements.
 *
 * Initializes a Arrays object and assigns $items the supplied values.
 *
 * @param mixed $items Elements
 */
public static function create(array $items = []): Arrays
```

**Examples**

```php
$arrays = Arrays::create([
                        'movies' => [
                           'the_thin_red_line' => [
                               'title' => 'The Thin Red Line',
                               'directed_by' => 'Terrence Malick',
                               'produced_by' => 'Robert Michael, Geisler Grant Hill, John Roberdeau',
                               'decription' => 'Adaptation of James Jones autobiographical 1962 novel, focusing on the conflict at Guadalcanal during the second World War.'
                           ],
                           'bad_times_at_the_el_royale' => [
                               'title' => 'Bad Times at the El Royale',
                               'directed_by' => 'Drew Goddard',
                               'produced_by' => 'Drew Goddard, Steve Asbell',
                               'decription' => 'Early 1970s. Four strangers check in at the El Royale Hotel. The hotel is deserted, staffed by a single desk clerk. Some of the new guests reasons for being there are less than innocent and some are not who they appear to be.'
                           ]
                        ]
                    ]);
```

##### <a name="arrays_chunk"></a> Method: `chunk()`

```php
/**
 * Create a chunked version of current array.
 *
 * @param int  $size         Size of each chunk.
 * @param bool $preserveKeys Whether array keys are preserved or no.
 */
public function chunk($size, $preserveKeys = false): self
```

**Examples**

```php
$arrays = Arrays::create(['a', 'b'])->chunk(2)->toArray();
```

##### <a name="arrays_combine"></a> Method: `combine()`

```php
/**
 * Create an array using the current array as keys and the other array as values.
 *
 * @param array $array Values array
 */
public function combine(array $array): self
```

**Examples**

```php
$arrays = Arrays::create(['green', 'red', 'yellow'])->combine(['avacado', 'apple', 'banana'])->toArray();
```

### Tests

Run tests

```
./vendor/bin/pest
```

### License
[The MIT License (MIT)](https://github.com/atomastic/arrays/blob/master/LICENSE)
Copyright (c) 2020 [Sergey Romanenko](https://github.com/Awilum)
