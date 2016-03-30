thunderbird
===========

Ansible role for installing Thunderbird beta on Debian and Ubuntu.
For Ubuntu, a PPA will be used, and for Debian, the latest tarball will be
downloaded, extracted, symlinked to /usr/local/bin.

Role Variables
--------------
```
thunderbird_lang: en-US
thunderbird_arch: linux64
thunderbird_version: 45.45.0b3
thunderbird_download_base_url: "https://download.mozilla.org/?product=thunderbird"
thunderbird_download_url: "{{ thunderbird_download_base_url }}-{{ thunderbird_version }}-SSL&os={{ thunderbird_arch }}&lang={{ thunderbird_lang }}"

thunderbird_download_directory: /usr/local/src
thunderbird_download_tarball: "thunderbird-beta-latest-{{ thunderbird_arch }}-{{ thunderbird_lang }}.tar.bz2"

# Base directory into which thunderbird will be installed. A subdirectory
# name "thunderbird" will be automatically created during tarball extraction.
thunderbird_install_directory: /opt

thunderbird_create_symlink: true
thunderbird_symlink_src: "{{ thunderbird_install_directory }}/thunderbird/thunderbird"
thunderbird_symlink_dest: /usr/local/bin/thunderbird
```

Example Playbook
----------------
```
- name: Install Thunderbird
  hosts: workstations
  roles:
    - role: conorsch.thunderbird
```

License
-------

MIT
