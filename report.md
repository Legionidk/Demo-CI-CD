# Билды

[красный](https://github.com/Legionidk/Demo-CI-CD/actions/runs/39926249239) / [коммит](https://github.com/Legionidk/Demo-CI-CD/commit/40456cf847acd6c3366c35870cffff46e15cf35b)

[зеленый](https://github.com/Legionidk/Demo-CI-CD/actions/runs/39926398629) / [коммит](https://github.com/Legionidk/Demo-CI-CD/commit/af8d03386cca765e59ace77daed151899b5592bf)

# Прогноз

Ставлю на то, что не пройдет `test_stylesheet_exists`.

Результат: да я чертов гений, он не прошел.

```
test_stylesheet_exists (test_site.SiteTests.test_stylesheet_exists) ...
  test_stylesheet_exists (test_site.SiteTests.test_stylesheet_exists) (href='missing.css') ... FAIL

  FAIL: test_stylesheet_exists (test_site.SiteTests.test_stylesheet_exists) (href='missing.css')
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/runner/work/Demo-CI-CD/Demo-CI-CD/tests/test_site.py", line 54, in test_stylesheet_exists
    self.assertTrue(bool(href) and (SITE / href).is_file(),
AssertionError: False is not true : Missing stylesheet: missing.css
```

После падения тестов, шаги `Build Site`, `Save site artifact` и `Post Prepare Python` автоматически отменились.

# Где выполнялись тесты?

Тесты выполнялись в облаке на **GitHub**, поэтому они доступны не только на локальном компе.

# Почему зелёный результат после смены аудитории не доказывает отсутствие ошибки?

Потому что у нас нет теста на проверку аудитории, я туда все что угодно написать могу.
