# Mindful Analysis

[![ci][ci_badge]][ci_badge_link]
[![pub package][pub_badge]][pub_badge_link]
[![License: MIT][license_badge]][license_badge_link]
[![style: mindful analysis][badge]][badge_link]

---

This package provides lint rules for Dart and Flutter which are used at [Mindful Software][mindful_software_link]. For more information, see the [complete list of options][analysis_options_yaml].

**Note**: This package was heavily inspired by [pedantic][pedantic_link] via VGV.

## Usage

To use the lints, add as a dev dependency in your `pubspec.yaml`:

```yaml
dev_dependencies:
  mindful_analysis: ^4.0.0
```

Then, add an include in `analysis_options.yaml`:

```yaml
include: package:mindful_analysis/analysis_options.yaml
```

This will ensure you always use the latest version of the lints. If you wish to restrict the lint version, specify a version of `analysis_options.yaml` instead:

```yaml
include: package:mindful_analysis/mindful_analysis_options.1.0.0.yaml
```

## Suppressing Lints

There may be cases where specific lint rules are undesirable. Lint rules can be suppressed at the line, file, or project level.

An example use case for suppressing lint rules at the file level is suppressing the `prefer_const_constructors` in order to achieve 100% code coverage. This is due to the fact that const constructors are executed before the tests are run, resulting in no coverage collection.

### Line Level

To suppress a specific lint rule for a specific line of code, use an `ignore` comment directly above the line:

```dart
// ignore: public_member_api_docs
class A {}
```

### File Level

To suppress a specific lint rule of a specific file, use an `ignore_for_file` comment at the top of the file:

```dart
// ignore_for_file: public_member_api_docs

class A {}

class B {}
```

### Project Level

To suppress a specific lint rule for an entire project, modify `analysis_options.yaml`:

```yaml
include: package:mindful_analysis/analysis_options.yaml
linter:
  rules:
    public_member_api_docs: false
```

## Badge

To indicate your project is using `mindful_analysis` →
[![style: mindful analysis][badge]][badge_link]

```md
[![style: mindful analysis](https://img.shields.io/badge/style-mindful_analysis-B22C89.svg)](https://pub.dev/packages/mindful_analysis)
```

[analysis_options_yaml]: https://github.com/michaelbushe/mindful_analysis/blob/main/lib/analysis_options.1.0.0.yaml
[ci_badge]: https://github.com/VeryGoodOpenSource/mindful_analysis/workflows/ci/badge.svg
[ci_badge_link]: https://github.com/VeryGoodOpenSource/mindful_analysis/actions
[badge]: https://img.shields.io/badge/style-mindful_analysis-B22C89.svg
[badge_link]: https://pub.dev/packages/mindful_analysis
[license_badge]: https://img.shields.io/badge/license-MIT-blue.svg
[license_badge_link]: https://opensource.org/licenses/MIT
[pedantic_link]: https://github.com/dart-lang/pedantic
[pub_badge]: https://img.shields.io/pub/v/mindful_analysis.svg
[pub_badge_link]: https://pub.dartlang.org/packages/mindful_analysis
[mindful_software_link]: https://mindfulsoftware.com
