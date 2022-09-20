# aws-profile-manager

aws-profile-manager is a Python script for loading, tracking, and unloading AWS profile credentials so they are usable by terraform et al. It allows for selecting credentials stored in `~/.aws/credentials` and setting them as environment variables without having export statments in your history.

## Installation

Clone the repo, install dependencies, run the script.

## Usage

```bash
# list profiles
$ aws-profile-manager --list
default
private
work.admin
work.dev

# fetch work.dev
$ eval $( aws-profile-manager --fetch work.dev )
AWS profile 'work.dev' activated.

# check status
$ aws-profile-manager --status
Active profile: work.dev

# switch to work.admin
$ eval $( aws-profile-manager --fetch work.admin )
AWS profile 'work.admin' activated.

# clear all profile data from the environment
$ eval $( aws-profile-manager --clean )
All AWS environment variables cleaned.
$ aws-profile-manager --status
No active AWS profile.
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)