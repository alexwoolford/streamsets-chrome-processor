# streamsets-chrome-processor

This processor uses headless Chrome to make page requests.

* input: `/url`, e.g. http://www.example.com
* output: `/pageSource`, i.e. the HTML for that page


The Chrome browser and Chromedriver must be installed on the host(s) that run this processor.

On OSX, `brew install chromedriver`; on CentOS `yum install chromedriver`.

Install Chrome. On CentOS:

    vi /etc/yum.repos.d/google-chrome.repo

    [google-chrome]
    name=google-chrome - x86_64
    baseurl=http://dl.google.com/linux/chrome/rpm/stable/x86_64
    enabled=1
    gpgcheck=1
    gpgkey=https://dl.google.com/linux/linux_signing_key.pub
    
    yum install google-chrome-stable

If SDC security is enabled, grant permissions to the SDC user-libs folder by adding the following to `/etc/sdc/sdc-security.policy`:

    grant codebase "file://${sdc.dist.dir}/user-libs/-" {
      permission java.security.AllPermission;
    };
