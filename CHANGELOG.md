# Changelog

All notable changes to this project are documented in this file.

## [3.0.0] - 2026-07-22

### Added

- Full **typed public API** (parameters and return types on `ImageResize`).
- **PHPStan** (level 3) and **PSR-12** (PHP-CS-Fixer) in development; CI static-analysis job.
- PHPUnit 10+ configuration migration; tests on PHP 8.2–8.5.
- Additional tests: missing file, `allow_enlarge`, `exact_size` save, WebP/AVIF save, gamma save, stronger filter test.

### Changed

- **Minimum PHP version: 8.1** (`ext-gd`, `ext-fileinfo` required).
- `ImageResize::__construct()` requires `string $filename` (non-empty path, `data:` URL, or valid file).
- `save()` documents `array|false $exact_size` for fixed canvas output.
- `chmod` after save only when saving to a file path string.
- Open `finfo` only when `getimagesize()` fails (faster loads on success path).

### Fixed

- BMP save no longer passes `null` to `imagebmp()` (PHP 8.5 deprecation).
- Removed `finfo_close()` (deprecated in PHP 8.5).
- Constructor no longer uses an invalid `return` statement.

### Removed

- Support for PHP versions below 8.1 (use `2.x` releases).

[3.0.0]: https://github.com/gumlet/php-image-resize/compare/2.1.0...3.0.0
