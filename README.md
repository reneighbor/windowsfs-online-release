# windowsfs-online-release

A [BOSH](http://docs.cloudfoundry.org/bosh/) release for deploying:
* [windows2019fs](https://github.com/cloudfoundry-incubator/windows2016fs/tree/master/2019).

**Note:**

This release assumes your BOSH installation has internet access at deploy time.

## smoke test

Ensure that `winc-release` and `windowsfs-release` are uploaded to your BOSH director.

2019 example:
```
bosh -d windows2019fs deploy manifests/smoke-test-2019.yml
bosh -d windows2019fs run-errand smoke-test
```

## Requirements

* This bosh release can only be deployed together with a [winc-release](https://github.com/cloudfoundry/winc-release) of v2.0 or higher. The [windows2019fs pre-start script](/jobs/windows2019fs/templates/pre-start.ps1.erb) waits for winc-release's groot pre-start to signal.
