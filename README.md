# Sample BOSH release for Python/Virtualenv and Flask web framework

This BOSH release is a demonstration of packaging Python and using Virtualenv to locally package the `requirements.txt` pips for an application.

Huge thanks to @antonsoroko for https://github.com/antonsoroko/simple-flask-app-bosh. I have taken his work and upgraded it for bosh2 deployment manifest, and included the blobs within the release.

## Install

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=simple-python-flask-app
bosh deploy manifests/sample-python-flask-app.yml --vars-store tmp/creds.yml
```

If your BOSH has Credhub, then you can omit `--vars-store` flag. It is used to generate any passwords/credentials/certificates required by `manifests/sample-python-flask-app.yml`.


## Development

As a developer of this release, create new releases, upload and deploy them:

```
bosh create-release --force && \
  bosh -n upload-release && \
  bosh deploy manifests/sample-python-flask-app.yml --vars-store tmp/creds.yml
```

If your BOSH has Credhub, then you can omit `--vars-store` flag. It is used to generate any passwords/credentials/certificates required by `manifests/sample-python-flask-app.yml`.
