��DLL�Ăяo��SAORI�ucall_func�v
������͉��H
�u�f���v�p�S�[�X�g��SAORI�ł��B
�C�ӂ�DLL���G�N�X�|�[�g����֐����Ăяo�����Ƃ��ł��܂��B

���ڎ�
�@������͉��H
�@���ڎ�
�@���g����
�@�@// [��{]
�@�@�@��add_func
�@�@�@��call_func
�@�@�@��call_func_ex
�@�@�@��remove_func
�@�@// [����������]
�@�@�@��alloc_mem
�@�@�@��get_mem
�@�@�@��get_mem_ex
�@�@�@��set_mem
�@�@�@��set_mem_ex
�@�@�@��free_mem
�@�@�@��calc_offset
�@�@// [�\���̑���]
�@�@�@��add_struct
�@�@�@��remove_struct
�@�@�@��alloc_struct
�@�@�@��free_struct
�@�@�@��get_struct_addr
�@�@�@��set_struct_val_all
�@�@�@��set_struct_val
�@�@�@��get_struct_val
�@���^�̖��O
�@�����ł̃T���v��
�@���ӎ�
�@�����C�Z���X
�@������m�F��
�@���A����
�@������


���g����
��(�e�R�}���h�������̃t�H�[�}�b�g)�F
��Argument0
�EArgument1
�EArgument2
�EArgument[n]
...
��Result
�`�R�}���h�������`

// [��{]
��add_func
�EDLL��
�E�֐���
�E�Ԃ�l�^
�E�����^1
�E�����^2
...
���Ȃ�
�w��̊֐���o�^���Ďg�p�\�ɂ��܂��B
�֐��͕W���Ăяo���K��(stdcall)�̂��̂����A����ɌĂяo���܂���B
�^�̎w��̎d���́A��q�́u�^�̖��O�v���Q�Ƃ��Ă��������B

��call_func
�E�֐���
�E����1
�E����2
...
���֐��̕Ԃ�l
�o�^���ꂽ�w��̊֐����Ăяo���܂��B
������DLL�œ������O�̊֐�������ƁA�ǂꂩ���Ăяo����܂��B
�ǂꂪ�Ăяo����邩�͕s��ł��B
���̂悤�ȏꍇ�́ucall_func_ex�v���g�p���Ă��������B

��call_func_ex
�E�֐���
�EDLL��
�E����1
�E����2
...
���֐��̕Ԃ�l
�o�^���ꂽ�w��̊֐����Ăяo���܂��B
�o�^���ꂽ�w���DLL�̊֐����Ăяo���܂��B
������DLL�œ������O�̊֐�������ꍇ�́A��������g�p���Ă��������B

��remove_func
�E�֐���
�EDLL��
���Ȃ�
�o�^���ꂽ�w��̊֐����폜���܂��B
DLL�����ȗ����ꂽ�ꍇ�́A�֐����Ɉ�v���邷�ׂĂ̓o�^�ς݊֐����폜����܂��B
DLL�����w�肳��Ă���ꍇ�́A����DLL�̂��̂����폜���܂��B


// [����������]
��alloc_mem
�E�^
�E�ǉ����1
�E�ǉ����2
���|�C���^(�������A�h���X)
�w�肳�ꂽ�^�ɍ��킹���������̈���m�ۂ��ĕԂ��܂��B
�^������/�����̎��́A�ǉ����1�ɏ����l���w�肷�邱�Ƃ��o���܂�(�ȗ��\)�B
�^���|�C���^(p)�̎��́A�ǉ����1�ɃT�C�Y���w�肵�Ȃ���΂Ȃ�܂���B�����l�͎w��ł��܂���B
�^��������(s/uni/cs/cu)�̎��́A�ǉ����1�ɏ����l���A�ǉ����2�ɃT�C�Y���w�肷�邱�Ƃ��o���܂�(�ȗ��\)�B
�������A�T�C�Y���w�肵�����ꍇ�́A�󕶎���ł��ǂ��̂ŏ����l���w�肵�Ȃ��Ƃ����܂���B
�Ȃ��A�����l���狁�߂��T�C�Y�ƁA�ǉ����2�Ɏw�肳�ꂽ�T�C�Y�͂��傫�������̗p����܂��B

�m�ۂ����������́A�K���ufree_mem�v�ŉ�����Ă��������B

��get_mem
�E�|�C���^
�E�^
���|�C���^�̓��e
�w�肳�ꂽ�|�C���^�̓��e���擾���܂��B
������(s/uni/cs/cu)���w�肳�ꂽ�Ƃ��́A�k���I�[�܂Ŏ擾���܂��B
�^��p/v���w�肳�ꂽ�Ƃ��́A�G���[�ɂȂ�A�����擾���܂���B

��get_mem_ex
�E�|�C���^
�E�I�t�Z�b�g
�E�^(�|�C���^)
�E�^(�I�t�Z�b�g)
���|�C���^�̓��e
�w�肳�ꂽ�|�C���^����A�I�t�Z�b�g�������ꂽ�ʒu�̃������̓��e���擾���܂��B
�����Ł@�|�C���^+sizeof(�^(�I�t�Z�b�g))*�I�t�Z�b�g�@�����̌v�Z�����Ă��܂��B
�^(�I�t�Z�b�g)���ȗ����ꂽ�ꍇ�́A�@�|�C���^+�I�t�Z�b�g�@�Ōv�Z���܂��B
������(s/uni/cs/cu)���w�肳�ꂽ�Ƃ��́A�k���I�[�܂Ŏ擾���܂��B
�^(�I�t�Z�b�g)��v���w�肳�ꂽ�Ƃ��A�������͌^(�|�C���^)��p/v���w�肳�ꂽ�Ƃ��́A�G���[�ɂȂ�A�����擾���܂���B

��set_mem
�E�l
�E�|�C���^
�E�^
���Ȃ�
�w�肳�ꂽ�|�C���^�̓��e���w��̒l�ɐݒ肵�܂��B
�^��p/v���w�肳�ꂽ�Ƃ��́A�G���[�ɂȂ�A�����ݒ肵�܂���B

��set_mem_ex
�E�l
�E�|�C���^
�E�^(�|�C���^)
�E�^(�I�t�Z�b�g)
���Ȃ�
�w�肳�ꂽ�|�C���^����A�I�t�Z�b�g�������ꂽ�ʒu�̃������̓��e���w��̒l�ɐݒ肵�܂��B
�����Ł@�|�C���^+sizeof(�^(�I�t�Z�b�g))*�I�t�Z�b�g�@�����̌v�Z�����Ă��܂��B
�^(�I�t�Z�b�g)���ȗ����ꂽ�ꍇ�́A�@�|�C���^+�I�t�Z�b�g�@�Ōv�Z���܂��B
�^(�I�t�Z�b�g)��v���w�肳�ꂽ�Ƃ��A�������͌^(�|�C���^)��p/v���w�肳�ꂽ�Ƃ��́A�G���[�ɂȂ�A�����ݒ肵�܂���B

��free_mem
�E�|�C���^
�E�^
���Ȃ�
alloc_mem�Ŋm�ۂ����̈���J�����܂��B

��calc_offset
�E�^1
�E�^2
...
���I�t�Z�b�g�l
�w�肳�ꂽ�^�̃��X�g����߂�̈�̃T�C�Y��Ԃ��܂��B
�������̈�ɕ����̒l�����݂��A�^���o���o���̎��A
���̔C�ӂ̉ӏ��ɂ���l�̃|�C���^���A�������̈�擪�ւ̃|�C���^���狁�߂�ۂɗ��p�ł��܂��B

// [�\���̑���]
��add_struct
�E�\���̖�
�E�^1
�E�^2
...
���Ȃ�
�\���̂�o�^����alloc_struct�Ŏg�p�\�ɂ��܂��B
�^1�ȍ~�͍\���̂Œ�`���ꂢ��e�����o�̌^�����Ɏw�肵�Ă��������B
�^���w�肷��ہA���p�X�y�[�X�ŋ�؂�A�K���ȕ�������w�肷�邱�ƂŁA
���̕�����������o�̎��ʎq�Ƃ��ė��p�ł��܂��B
��̍\���̂̒��ŁA�������ʎq���قȂ郁���o�ɗp���邱�Ƃ͏o���܂���B
�����A�������ʎq���w�肵���ꍇ�͌�̕����L���ɂȂ�܂��B
��F�ui16 count�v�Ǝw�肷��ƁA�^�́ui16�v�A���ʎq�́ucount�v�ƂȂ�܂��B

�Ȃ��A�\���̂ɂ����Ċe�f�[�^�̃o�C�g���E�ւ̔z�u�͍l������܂���B
�u#pragma pack(push, 1)�v�����ł��B

��remove_struct
�E�\���̖�
���Ȃ�
�o�^���ꂽ�\���̂��폜���܂��B

��alloc_struct
�E�\���̖�
���\���̊Ǘ��ԍ�
�o�^���ꂽ�\���̂����Ƃɂ��āA�������̈���m�ۂ��܂��B
�\���̂ւ̃|�C���^���֐��̈����Ƃ��Ďg���Ƃ��́A
get_struct_addr�ō\���̊Ǘ��ԍ�����|�C���^���擾���Ă��������B

��free_struct
�E�\���̊Ǘ��ԍ�
���Ȃ�
�\���̂Ƃ��Ċm�ۂ����������̈���J�����܂��B

��get_struct_addr
�E�\���̊Ǘ��ԍ�
���|�C���^
�\���̊Ǘ��ԍ�����|�C���^(�������̈�̃A�h���X)���擾���܂��B
���̃|�C���^��alloc_mem�Ŏ擾�������̂Ɠ��l�Ɉ����܂��B
�������Afree_mem�ɂ͎g��Ȃ��ł��������B

��set_struct_val_all
�E�\���̊Ǘ��ԍ�
�E�l1
�E�l2
...
���Ȃ�
�w��̍\���̂̂��ׂẴ����o�ɑ΂��Ēl��ݒ肵�܂��B
�w�肳�ꂽ�l�������o��菭�Ȃ��ꍇ�A��ɂ��郁���o��0���w�肳�ꂽ�ƌ��Ȃ��܂��B
�����o��葽���ꍇ�A�������͖�������܂��B

��set_struct_val
�E�\���̊Ǘ��ԍ�
�E���ʎq�^����
�E�l
���Ȃ�
�w��̍\���̂̃����o�ɑ΂��Ēl��ݒ肵�܂��B
�����o��add_struct�Ŏw�肵�����ʎq���A�擪���牽�Ԗڂ̃����o���Ƃ��������Ŏw�肵�܂��B
������1����n�܂�܂��B

��get_struct_val
�E�\���̊Ǘ��ԍ�
�E���ʎq�^����
���l
�w��̍\���̂̃����o����l���擾���܂��B
�����o��add_struct�Ŏw�肵�����ʎq���A�擪���牽�Ԗڂ̃����o���Ƃ��������Ŏw�肵�܂��B
������1����n�܂�܂��B

���^�̖��O
�^�͕�����Ŏw�肵�܂��B
�^���w�肷�镶����́M�Œ��O����v�f�Ŕ��f����܂��B
�ꗗ�ɂ��镶����ȊO�����ɕt�������Ă��F������܂��B
�ꗗ�ɂȂ����̂́uv�v�Ƃ��Ĉ����܂��B
�Ȃ��A���̂Ƃ���Aconst���Ƃ����łȂ����̂̋�ʂ͂��Ă��܂���B

������  �^
v       void(�Ԃ�l/��������)
i       32�r�b�g�����t������
i8      8�r�b�g�����t������
i16     16�r�b�g�����t������
i64     64�r�b�g�����t������
u       32�r�b�g�����Ȃ�����
u8      8�r�b�g�����Ȃ�����
u16     16�r�b�g�����Ȃ�����
u64     64�r�b�g�����Ȃ�����
r       64�r�b�g��������
r32     32�r�b�g��������
c       char
w       wchar_t
s       char*
uni     wchar_t*
cs      const char*
cu      const wchar_t*
p       �|�C���^(�A�h���X)


�����ł̃T���v��
#define CALL_FUNC_SAORI 'call_func.dll'
// Win32API��MessageBox���Ă�
	// �֐���o�^
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','user32.dll','MessageBoxA','i32','i32','cstr','cstr','i32')
	// �֐��̌Ăяo��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','MessageBoxA',0,'test1','test1',0)
	// �֐����폜
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','MessageBoxA')
	// �폜����Ă���̂ł��̌Ăяo���͎��s����
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','MessageBoxA',0,'test1','test1',0)

// Win32API��GetDC���Ăяo��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','user32.dll','GetDC','u32','u32')
	// GetDC(0)�̕Ԃ�l(�f�X�N�g�b�v�̃f�o�C�X�R���e�L�X�g)���Ԃ�
	_hdc = FUNCTIONEX(CALL_FUNC_SAORI,'call_func_ex','GetDC','user32.dll',0)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','GetDC','user32.dll)
	// HDC�o��
	"%(_hdc)"

// Win32API��GetLocalTime���Ăяo��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','kernel32.dll','GetLocalTime','v','p')
	// �������m��
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_mem','p',16)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','GetLocalTime',_a)
	// �������擪��WORD�l��ǂ�
	_year = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'u16')
	// �������擪����2�o�C�g���u16�l��ǂ�
	_month = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,2,'u16')
	// �������擪����u16�l3����̂�u16�l��ǂ�
	_day = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,3,'u16','u16')
	// ���������
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_mem',_a,'p')	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','GetLocalTime')
	// ���t�o��
	"%(_year)/%(_month)/%(_day)"

// Win32API��GetCurrentDirectory���Ăяo��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','kernel32.dll','GetCurrentDirectoryA','u32','u32','ptr')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_mem','p',260)	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','GetCurrentDirectoryA',260,_a)
	_path = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'s')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_mem',_a,'p')	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','GetCurrentDirectoryA')
	// �p�X�o��
	"%(_path)"

// �������ɒl�����ĕʂ̌^�Ŏ��o��
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_mem','u32',0x00018002)	
	// ���ʂ�i16�l�����o��
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'i16')
	// ��ʂ�u16�l�����o��
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,1,'u16','u16')
	// ���ʂ�i16�l������
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_mem',-1,_a,'i16')
	// ��ʂ�i16�l������
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_mem_ex',-2,_a,1,'i16','i16')
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'u16')
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,1,'u16','u16')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_mem',_a,'p')
	"%(_b)  %(_c)  %(_d)  %(_e)"

// �\���̗��p��
	// ���ʎq���g��Ȃ�
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','TEST','i32','i16','u32')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','TEST')
	// �����o�����ꂼ��1,2,3�ŏ�����
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val_all',_a,1,2,3)
	// �e�����o�������ɂ���ēǂݏ���
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,1)
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,2)
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,3)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val',_a,2,100)
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,2)
	// �m�ۂ����\���̂̃������̈���J��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_struct',_a)
	// �\���̂̓o�^�����폜
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_struct','TEST')
	"%(_b)  %(_c)  %(_d)  %(_e)\n"
	--
	// ���ʎq���g��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','TEST2','i32 abd','i16 ddd','u32 fds')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','TEST2')
	// �����o�����ꂼ��1,2,3�ŏ�����
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val_all',_a,1,2,3)
	// �e�����o�����ʎq�ɂ���ēǂݏ���
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'abd')
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'ddd')
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'fds')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val',_a,'ddd',100)
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'ddd')
	// �m�ۂ����\���̂̃������̈���J��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_struct',_a)
	// �\���̂̓o�^�����폜
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_struct','TEST2')
	"%(_b)  %(_c)  %(_d)  %(_e)\n"

// CreateProcess���Ăяo��
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','kernel32.dll','CreateProcessA','i32','cstr','str','p','p','i32','u32','p','p','p','p')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','STARTUPINFO','u32 cb','str','str','str','u32','u32','u32','u32','u32','u32','u32','u32','u16','u16','p','u32','u32','u32')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','PROCESS_INFORMATION','u32','u32','u32','u32')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','STARTUPINFO')
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','PROCESS_INFORMATION')
	// �K�v�ȃ����o�ɂ����l������
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val',_a,'cb',68)
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_addr',_a)
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_addr',_b)
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','CreateProcessA','C:\WINDOWS\SYSTEM32\CALC.EXE','',0,0,0,0,0,0,_c,_d)
	// �\���̂�������擾
	_hProcess = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_b,1)
	_hThread = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_b,2)
	_ProcessId = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_b,3)
	_ThreadId = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_b,4)
	
	"%(_e)\n%(_hProcess)  %(_hThread)  %(_ProcessId)  %(_ThreadId)\n"
	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','CreateProcessA')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_struct',_a)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_struct',_b)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_struct','PROCESS_INFORMATION')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_struct','STARTUPINFO')

���ӎ�
SAORI�̃t���[�����[�N�̍쐬/���J�ƍ쐬�Ɋւ���A�h�o�C�X�����������ł�񎁂Ɋ��ӂ��܂��B


�����C�Z���X
NYSL Version 0.9982�ɏ]���܂��B

http://www.kmonos.net/nysl/
NYSL Version 0.9982
----------------------------------------
A. �{�\�t�g�E�F�A�� Everyone'sWare �ł��B���̃\�t�g����ɂ�����l��l���A
   �������̍�������̂������̂Ɠ����悤�ɁA���R�ɗ��p���邱�Ƃ��o���܂��B

  A-1. �t���[�E�F�A�ł��B��҂���͎g�p������v�����܂���B
  A-2. �L��������}�̂̔@�����킸�A���R�ɓ]�ځE�Ĕz�z�ł��܂��B
  A-3. �����Ȃ��ނ� ���ρE���v���O�����ł̗��p ���s���Ă��\���܂���B
  A-4. �ύX�������̂╔���I�Ɏg�p�������̂́A���Ȃ��̂��̂ɂȂ�܂��B
       ���J����ꍇ�́A���Ȃ��̖��O�̉��ōs���ĉ������B

B. ���̃\�t�g�𗘗p���邱�Ƃɂ���Đ��������Q���ɂ��āA��҂�
   �ӔC�𕉂�Ȃ����̂Ƃ��܂��B�e���̐ӔC�ɂ����Ă����p�������B

C. ����Ґl�i���� ����܂�(whiteball) �ɋA�����܂��B���쌠�͕������܂��B

D. �ȏ�̂R���́A�\�[�X�E���s�o�C�i���̑o���ɓK�p����܂��B


������m�F��
WinXP SP3/Visual C++ 2005 Express Edition
SSP2.00.22+aya5�œ���m�F�B


���A����
��Җ��E���炽��
�T�C�g�EJUNK ROOM
http://whiteball.m7.coreserver.jp/
���[���A�h���X
white_ball_11�@hotmail.com
�͂Ăȃ_�C�A���[
http://d.hatena.ne.jp/white-ball/


������
11/03/15    Ver.0.4    �\���̊֌W�̃R�}���h��ǉ�(calc_offset,add_struct,remove_struct,alloc_struct,free_struct,get_struct_addr,set_struct_val_all,set_struct_val,get_struct_val)
09/03/07    Ver.0.3    alloc_mem�ŏ����l���ȗ��ł��Ȃ��s����C��
09/03/01    Ver.0.2    �����̂Ȃ��֐����Ăяo�����Ƃ���ƃG���[�ɂȂ��Ă����s����C��
                       SAORI�̂���t�H���_�ɂ���DLL��ǂݍ��߂Ȃ������s����C��
09/02/15    Ver.0.1    ���J
