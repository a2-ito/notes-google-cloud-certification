# Network

## Google Cloud Services
### VPC: Virtual Private Cloud
  - Cloud VPN�g���l���܂���Cloud Interconnect�A�^�b�`�����g(VLAN)���o�R���ăg���t�B�b�N�����[�e�B���O���邱�Ƃɂ��A�I���v���~�X����Google API�ƃT�[�r�X�ɐڑ��ł���
  - �I���v���~�X���瑗�M�����Google API�ƃT�[�r�X�g���t�B�b�N��private.googleapis.com�܂���restricted.googleapis.com �Ƃ������ʂȃh���C�����C���̂����ꂩ�Ɋ֘A�t����ꂽIP�A�h���X�ɓ]������K�v������
- auto mode �� custom mode
  - auto mode
    - �e���[�W��������1�̃T�u�l�b�g���l�b�g���[�N���Ɏ����I�ɍ쐬�����
  - custom mode
    - �T�u�l�b�g�͎����I�ɍ쐬����Ȃ�
- �G�C���A�XIP
  - ����IP�A�h���X�͈̔͂��G�C���A�X�Ƃ��Ċ����\
  - VM�ŕ����T�[�r�X�����s���Ă���ꍇ�A�e�T�[�r�X�ɈقȂ�IP�A�h���X�����蓖�Ă�ƕ֗�
- �l�b�g���[�N�^�O���\�����āA�����VM�C���X�^���X�ɓK�p�����t�@�C�A�E�H�[�����[���⃋�[�g���쐬�ł���B
- Private Service Connect �v���C�x�[�g�T�[�r�X�A�N�Z�X
  - �T�|�[�g����Google�T�[�r�X
    - Cloud SQL
    - Memorystore for Redis
    - Memorystore for Memcached
    - AI Platform Training
    - Cloud Build

### Shared VPC
- �g�D���̕����v���W�F�N�g�̃��\�[�X�����ʂ�VPC�ɐڑ�����
- BGP�ݒ�̓z�X�g�v���W�F�N�g�̂݁B
- Firewall �Ȃǃl�b�g���[�N�|���V�̈ꌳ�Ǘ�
- �ڑ��\�ȃT�[�r�X�v���W�F�N�g����(�����l��)1000

### Cloud Load Balancer
- �e�ʃX�P�[���[�̐ݒ�
  - �^�[�Q�b�g�e�ʂ�ύX�����Ƀ^�[�Q�b�g�e�ʃX�P�[���_�E�����邱�Ƃ��ł���B
  - ��F�ő�g�p����80RPS�A�e�ʃX�P�[����0.5�̏ꍇ�A�L���ȃ^�[�Q�b�g�e�ʂ�40RPS�ƂȂ�B
- Global
  - Global External HTTP(S) Load Balancing
  - External HTTP(S) Load Balancing (classic)
  - SSL Proxy Load Balancing
  - TCP Proxy Load Balancing
    - PROXY�v���g�R����L���ɂ��邱�ƂŁA���M��IP�A�h���X�A����IP�A�h���X�A�|�[�g�ԍ����܂ޒǉ��w�b�_�[���C���X�^���X�փ��N�G�X�g�̍\�������Ƃ��đ��M����
- Regional
  - Regional External HTTP(S) Load Balancing

### Cloud Router

### Dedicated Interconnect
  - �O���[�o�����[�e�B���O���T�|�[�g
    - ����̃��[�W�����ւ� Interconnect ������΁A�����o�R�łǂ̃��[�W�����̃T�u�l�b�g�ɂ��A�N�Z�X�ł���悤�ɂȂ�
  - LOA-CFA: Letter of Authorization and Connecting Facility Assignment
    - Google����ڋq��NOC�i�Z�p�S���j�Ƀ��[���ő��M�����
    - LOA-CFA���x���_�[�ɑ��M���āA�x���_�[���ڑ����C���X�g�[���ł���悤�ɂ���K�v������
  - 10 Gbps or 100 Gbps �̉��
  - �Í�������Ȃ�

### Partner Interconnect
  - 50 Mbps �` 50 Gbps
  - �Í�������Ȃ�
  - L2 partner
    - BGP�̓I���v���~�X���[�^�[��VPC�l�b�g���[�N����Cloud Router �̊Ԃō\�������
  - L3 partner
    - �g���t�B�b�N�̓T�[�r�X�v���o�C�_�̃l�b�g���[�N�ɓn�����
    - �I���v���~�X�l�b�g���[�N�ƃT�[�r�X�v���o�C�_�l�b�g���[�N�̐ڑ��́A�T�[�r�X�v���o�C�_�ɂ���ĈقȂ�
      - BGP�Z�b�V�������m������K�v�����邩������Ȃ�

### Cloud IAM
  - Role Launch Stage
    - ALPHA, BETA, GA
    - GUI��ł͕\������Ȃ�
### Cloud Armor
- �v���r���[���[�h
  - ���[����K�p���Ȃ��Ă��A���̉e�����v���r���[�ł���B�v���r���[���[�h�ł́ACloud Monitoring �ɃA�N�V�������L�^�����B
- Network Load Balancer �ɂ͑Ή����Ă��Ȃ�
- 2�̃N���X

![Cloud Armor](https://raw.githubusercontent.com/a2-ito/notes-google-cloud-certification/master/images/cloudarmor_classes.png)

### Private Google Access
- ������J��Google�A�N�Z�X
- �O��IP�A�h���X�������Ȃ�VM�̃T�u�l�b�g�Ō�����J��Google�A�N�Z�X��L���ɂ���ƁAGoogle API�ƃT�[�r�X�Ŏg�p������A�̊O��IP�A�h���X��VM��ڑ��ł���

### ���^�f�[�^
- enable-os-login
  - os login ��L�����܂��͖������ł���

### route-based VPN tunnel
### policy-based VPN tunnel
### Cloud NAT

### Cloud DNS
- DNSSEC�𖳌��ɂ���
  - �h���C����DS���R�[�h���ׂĂ�e�]�[������폜����
    - ����ɂ���āA���]���o��DNSSEC���g�p���ăh���C���f�[�^�����؂��Ȃ��Ȃ�
  - DS���R�[�h�����W�X�g������폜���ꂽ��ADS���R�[�h�̍폜�����ׂẴ��]���o�ɓ`�������܂ő҂��Ă���A�]�[����DNSSEC���I�t�ɂ���K�v������

### VPC flow logs
- VM�C���X�^���X�ɂ���đ���M���ꂽ�l�b�g���[�N�t���[�̃T���v�����L�^�����
- �l�b�g���[�N���j�^�����O�A�t�H�����W�b�N�A���A���^�C���Z�L�����e�B���́A��p�̍œK���Ɏg�p�ł���

### Circuit Operational Status 

### Direct Peering
  - �I���v������Google�G�b�W�l�b�g���[�N�̊Ԃɒ��ڃs�A�����O�ڑ����\
  - Direct Peering �� Google Cloud �̊O���ɑ��݂���BGoogle Workspace �A�v���P�[�V�����ɃA�N�Z�X����K�v���Ȃ�����AGoogle Cloud �ւ̐����̃A�N�Z�X���@�́ADedicated Interconnect �܂��� Partner Interconnect �ƂȂ�B
### Career Peering

### Partner Interconnect
- �p�[�g�i�[�̎����Ă���L���p�V�e�B�ɉ����đш悪���܂�B

### Dedicated Interconnect

### GKE
- �m�[�h������̍ő�pod���́A�f�t�H���g��110
  - ���炷���Ƃ��\�B�i���₷���Ƃ͂ł��Ȃ��j
  - �m�[�h�ō쐬�ł��� Pod �̍ő呃��2�{�ȏ�̗��p�\��IP�A�h���X���w�肷�邱��
    - �m�[�h��pod���ǉ��E�폜�����ۂɁAKubernetes�ɂ��IP�A�h���X�̍ė��p��}���ł���
    - GKE �Ƃ����� Kubernetes �̃|���V�H
  - �f�t�H���g110�̏ꍇ�A/24 CIDR �����蓖�Ă�(256>110*2=220)

## Glossary
- ���[�e�B���O�v���g�R���n
  - IGP: Interior Gateway Protocol
    - RIP
      - (v1) �N���X�t���E���[�e�B���O�E�v���g�R���ɊY������Â��v���g�R��
    - OSPF
      - �����N�X�e�[�g���[�e�B���O���g�p����h���C�������[�e�B���O�v���g�R��
      - AS���Ŏ��s�����
    - EIGRP
    - IGRP
      - Cisco�Ǝ��v���g�R��
  - EGP: Exterior Gateway Protocol
    - BGP
      - �p�X�x�N�g�����[�e�B���O���g�p����h���C���ԃ��[�e�B���O�v���g�R��
      - AS�O�Ŏ��s�����
- VPC Flow log
- IKE: Internet Key Exchange
  - IKEv2 ���g�p����ƁA�g���t�B�b�N �Z���N�^���Ƃɕ����� CIDR ���w��ł���
  - v1
  - v2
- TFTP: Trivial File Transfer Protocol
  - UDP���g�����y�ʂȃt�@�C���]���v���g�R��



