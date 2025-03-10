# Changelog

## 4.3.0

### Added

- [Add `previously_force_updated?` #142](https://github.com/kufu/activerecord-bitemporal/pull/142)

### Changed

### Deprecated

### Removed

### Fixed

### Chores

- [Remove unneeded spec for Rails 5.x #143](https://github.com/kufu/activerecord-bitemporal/pull/143)

## 4.2.0

### Added

- [Allow passing `operated_at` to destroy #138](https://github.com/kufu/activerecord-bitemporal/pull/138)

### Changed

- [Change not to create history when destroying with `force_update` #135](https://github.com/kufu/activerecord-bitemporal/pull/135)
- [Raise `ValidDatetimeRangeError` instead of `RecordInvalid` in `_update_row` #136](https://github.com/kufu/activerecord-bitemporal/pull/136)

### Deprecated

### Removed

### Fixed

### Chores

- [Fix for RSpec deprecated warning #132](https://github.com/kufu/activerecord-bitemporal/pull/132)
- [Add some files to .gitignore #134](https://github.com/kufu/activerecord-bitemporal/pull/134)

## 4.1.0

### Added
- [add label option #127](https://github.com/kufu/activerecord-bitemporal/pull/127)

### Changed
- [Support for inverse_of of Rails 6.1 or higher #130](https://github.com/kufu/activerecord-bitemporal/pull/130)

### Deprecated

### Removed

### Fixed

## 4.0.0

### Breaking Changed

- [[proposal]When bitemporal_at exists inside the nest, the specified date was not prioritized, so the date of the inner bitemporal_at is now prioritized. #121](https://github.com/kufu/activerecord-bitemporal/pull/121)
- [Drop support Rails 5.2 #122](https://github.com/kufu/activerecord-bitemporal/pull/122)
- [Add required_ruby_version >= 2.7.0 #125](https://github.com/kufu/activerecord-bitemporal/pull/125)

### Added

- [Add support `bitemporal_callbacks` #123](https://github.com/kufu/activerecord-bitemporal/pull/123)

  ```rb
  class Employee < ActiveRecord::Base
    include ActiveRecord::Bitemporal
  
    after_bitemporal_create :log_create
    after_bitemporal_update :log_update
    after_bitemporal_destroy :log_destroy
  
    private
    
    def log_create
      puts "employee created"
    end

    def log_update
      puts "employee updated"
    end

    def log_destroy
      puts "employee destroyed"
    end
  end
  
  employee = Employee.create!(...) # => "employee created"
  employee.update!(...) # => "employee updated"
  employee.destroy! # => "employee destroyed"
  ```

### Changed

- [Update auto asgn #124](https://github.com/kufu/activerecord-bitemporal/pull/124)
- [Update License and CoC files #115](https://github.com/kufu/activerecord-bitemporal/pull/115)

### Deprecated

### Removed

- [Remove Gemfile.lock #126](https://github.com/kufu/activerecord-bitemporal/pull/126)
- [Remove test cases for using bitemporal_option_merge! of ActiveRecord:::Bitemporal::Callbacks #129](https://github.com/kufu/activerecord-bitemporal/pull/129)

### Fixed


## 3.0.0

### Breaking Changed
- [Assign updated bitemporal times to the receiver after update/destroy](https://github.com/kufu/activerecord-bitemporal/pull/118)

### Added

### Changed

### Deprecated

### Removed

### Fixed

## 2.3.0

### Breaking Changed

### Added
- [Add `InstanceMethods#swapped_id_previously_was`](https://github.com/kufu/activerecord-bitemporal/pull/114)

### Changed

### Deprecated

### Removed

### Fixed

## 2.2.0

### Breaking Changed

### Added
- [replace postgres docker image](https://github.com/kufu/activerecord-bitemporal/pull/103)
- [use Matrix Jobs in CircleCI](https://github.com/kufu/activerecord-bitemporal/pull/107)
- [Add support changing swapped_id, when called #destroy](https://github.com/kufu/activerecord-bitemporal/pull/110)

### Changed

### Deprecated

### Removed

### Fixed

## 2.1.0

### Breaking Changed

### Added
- [Update valid_to after #update](https://github.com/kufu/activerecord-bitemporal/pull/105)
- [Add GitHub Actions workflow to release to RubyGems.org](https://github.com/kufu/activerecord-bitemporal/pull/104)
- [migrate Scheduled workflows in CircleCI](https://github.com/kufu/activerecord-bitemporal/pull/106)

### Changed

### Deprecated

### Removed

### Fixed

## 2.0.0

### Breaking Changed
- [[Proposal] Changed valid_in to exclude valid_from = to and valid_to = from. by osyo-manga · Pull Request #95](https://github.com/kufu/activerecord-bitemporal/pull/95)

### Added

### Changed
- [[Proposal] Add range argument to .valid_allin. by Dooor · Pull Request #98](https://github.com/kufu/activerecord-bitemporal/pull/98)

### Deprecated

### Removed

### Fixed
- [Fix JOIN query does not have valid_from / valid_to when using .or. by osyo-manga · Pull Request #99](https://github.com/kufu/activerecord-bitemporal/pull/99)
- [Fix typo in README.md by Naoya9922 · Pull Request #101](https://github.com/kufu/activerecord-bitemporal/pull/101)

## 1.1.0

### Added

- [Add bitemporal data structure visualizer by wata727 · Pull Request #94](https://github.com/kufu/activerecord-bitemporal/pull/94)

### Changed

### Deprecated

### Removed

### Fixed

## 1.0.0

First stable release
