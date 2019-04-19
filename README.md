# villabajo_infra
villabajo Infra repository

Option 1:

ssh -i ~/.ssh/id_rsa -A m.sobolev@35.204.205.229 'ssh -tt 10.166.0.2'


Option 2:

in ~/.ssh/config write:

Host someinternalhost
  HostName 10.166.0.2
  ProxyCommand ssh -A bastion nc %h %p
  User m.sobolev

Host bastion
  HostName 35.204.205.229
  User m.sobolev

using as:

ssh someinternalhost
