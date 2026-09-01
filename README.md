# CloudBridge

CloudBridge is an Android cloud gallery / WhatsApp media backup project. This repository contains the corrected source package and CI build workflow.

## OAuth
- Release package: `com.cloudbridge.app`
- Android OAuth client: `553271654399-rg5dpgphnhbj4v8aelfl943802esnku4.apps.googleusercontent.com`
- Web OAuth client: `553271654399-svceue3g1t6ucrj3qcr0v8m5l7o22ufa.apps.googleusercontent.com`

OAuth client IDs are public identifiers. No client secret or production signing key is stored here.

## Important debug-login note
The CI debug APK uses package `com.cloudbridge.app.debug`. Google Sign-In will require a matching Android OAuth client for that debug package and its signing SHA-1. The existing Android OAuth client remains for the production package `com.cloudbridge.app`.

## Safety hardening
The corrected source verifies Google Drive file existence, size and MD5 checksum before marking a backup verified, and revalidates size/checksum immediately before local deletion. Restore uses Android MediaStore.
