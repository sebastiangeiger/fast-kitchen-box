# Fast Kitchen Box

This vagrant box is designed to spin up quickly, hence the correct version of
guest additions and chef (for my system) is already installed.

It is built on top of the basic test kitchen provided ubuntu 12.04 image.

To build it run `vagrant up` and then `vagrant package`.

## .kitchen.yml

Add this to your .kitchen.yml file (replace `{path-to-project}`):

```yaml
platforms:
  - name: ubuntu-12.04-fast
    driver:
      box_url: file://{path-to-project}/fast-kitchen-box/package.box
```
