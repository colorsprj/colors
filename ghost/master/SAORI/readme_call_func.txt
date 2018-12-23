＊DLL呼び出しSAORI「call_func」
■これは何？
「伺か」用ゴーストのSAORIです。
任意のDLLがエクスポートする関数を呼び出すことができます。

■目次
　■これは何？
　■目次
　■使い方
　　// [基本]
　　　●add_func
　　　●call_func
　　　●call_func_ex
　　　●remove_func
　　// [メモリ操作]
　　　●alloc_mem
　　　●get_mem
　　　●get_mem_ex
　　　●set_mem
　　　●set_mem_ex
　　　●free_mem
　　　●calc_offset
　　// [構造体操作]
　　　●add_struct
　　　●remove_struct
　　　●alloc_struct
　　　●free_struct
　　　●get_struct_addr
　　　●set_struct_val_all
　　　●set_struct_val
　　　●get_struct_val
　■型の名前
　■文でのサンプル
　■謝辞
　■ライセンス
　■動作確認環境
　■連絡先
　■履歴


■使い方
例(各コマンド説明文のフォーマット)：
●Argument0
・Argument1
・Argument2
・Argument[n]
...
＞Result
～コマンド説明文～

// [基本]
●add_func
・DLL名
・関数名
・返り値型
・引数型1
・引数型2
...
＞なし
指定の関数を登録して使用可能にします。
関数は標準呼び出し規約(stdcall)のものしか、正常に呼び出せません。
型の指定の仕方は、後述の「型の名前」を参照してください。

●call_func
・関数名
・引数1
・引数2
...
＞関数の返り値
登録された指定の関数を呼び出します。
複数のDLLで同じ名前の関数があると、どれかが呼び出されます。
どれが呼び出されるかは不定です。
このような場合は「call_func_ex」を使用してください。

●call_func_ex
・関数名
・DLL名
・引数1
・引数2
...
＞関数の返り値
登録された指定の関数を呼び出します。
登録された指定のDLLの関数を呼び出します。
複数のDLLで同じ名前の関数がある場合は、こちらを使用してください。

●remove_func
・関数名
・DLL名
＞なし
登録された指定の関数を削除します。
DLL名が省略された場合は、関数名に一致するすべての登録済み関数が削除されます。
DLL名が指定されている場合は、そのDLLのものだけ削除します。


// [メモリ操作]
●alloc_mem
・型
・追加情報1
・追加情報2
＞ポインタ(メモリアドレス)
指定された型に合わせたメモリ領域を確保して返します。
型が整数/実数の時は、追加情報1に初期値を指定することが出来ます(省略可能)。
型がポインタ(p)の時は、追加情報1にサイズを指定しなければなりません。初期値は指定できません。
型が文字列(s/uni/cs/cu)の時は、追加情報1に初期値を、追加情報2にサイズを指定することが出来ます(省略可能)。
ただし、サイズを指定したい場合は、空文字列でも良いので初期値も指定しないといけません。
なお、初期値から求めたサイズと、追加情報2に指定されたサイズはより大きい方が採用されます。

確保したメモリは、必ず「free_mem」で解放してください。

●get_mem
・ポインタ
・型
＞ポインタの内容
指定されたポインタの内容を取得します。
文字列(s/uni/cs/cu)を指定されたときは、ヌル終端まで取得します。
型にp/vが指定されたときは、エラーになり、何も取得しません。

●get_mem_ex
・ポインタ
・オフセット
・型(ポインタ)
・型(オフセット)
＞ポインタの内容
指定されたポインタから、オフセットだけ離れた位置のメモリの内容を取得します。
内部で　ポインタ+sizeof(型(オフセット))*オフセット　相当の計算をしています。
型(オフセット)が省略された場合は、　ポインタ+オフセット　で計算します。
文字列(s/uni/cs/cu)を指定されたときは、ヌル終端まで取得します。
型(オフセット)にvが指定されたとき、もしくは型(ポインタ)にp/vが指定されたときは、エラーになり、何も取得しません。

●set_mem
・値
・ポインタ
・型
＞なし
指定されたポインタの内容を指定の値に設定します。
型にp/vが指定されたときは、エラーになり、何も設定しません。

●set_mem_ex
・値
・ポインタ
・型(ポインタ)
・型(オフセット)
＞なし
指定されたポインタから、オフセットだけ離れた位置のメモリの内容を指定の値に設定します。
内部で　ポインタ+sizeof(型(オフセット))*オフセット　相当の計算をしています。
型(オフセット)が省略された場合は、　ポインタ+オフセット　で計算します。
型(オフセット)にvが指定されたとき、もしくは型(ポインタ)にp/vが指定されたときは、エラーになり、何も設定しません。

●free_mem
・ポインタ
・型
＞なし
alloc_memで確保した領域を開放します。

●calc_offset
・型1
・型2
...
＞オフセット値
指定された型のリストが占める領域のサイズを返します。
メモリ領域に複数の値が存在し、型がバラバラの時、
その任意の箇所にある値のポインタを、メモリ領域先頭へのポインタから求める際に利用できます。

// [構造体操作]
●add_struct
・構造体名
・型1
・型2
...
＞なし
構造体を登録してalloc_structで使用可能にします。
型1以降は構造体で定義されいる各メンバの型を順に指定してください。
型を指定する際、半角スペースで区切り、適当な文字列を指定することで、
その文字列をメンバの識別子として利用できます。
一つの構造体の中で、同じ識別子を異なるメンバに用いることは出来ません。
もし、同じ識別子を指定した場合は後の方が有効になります。
例：「i16 count」と指定すると、型は「i16」、識別子は「count」となります。

なお、構造体において各データのバイト境界への配置は考慮されません。
「#pragma pack(push, 1)」相当です。

●remove_struct
・構造体名
＞なし
登録された構造体を削除します。

●alloc_struct
・構造体名
＞構造体管理番号
登録された構造体をもとにして、メモリ領域を確保します。
構造体へのポインタを関数の引数として使うときは、
get_struct_addrで構造体管理番号からポインタを取得してください。

●free_struct
・構造体管理番号
＞なし
構造体として確保したメモリ領域を開放します。

●get_struct_addr
・構造体管理番号
＞ポインタ
構造体管理番号からポインタ(メモリ領域のアドレス)を取得します。
このポインタはalloc_memで取得したものと同様に扱えます。
ただし、free_memには使わないでください。

●set_struct_val_all
・構造体管理番号
・値1
・値2
...
＞なし
指定の構造体のすべてのメンバに対して値を設定します。
指定された値がメンバより少ない場合、後にあるメンバは0が指定されたと見なします。
メンバより多い場合、多い分は無視されます。

●set_struct_val
・構造体管理番号
・識別子／序数
・値
＞なし
指定の構造体のメンバに対して値を設定します。
メンバはadd_structで指定した識別子か、先頭から何番目のメンバかという序数で指定します。
序数は1から始まります。

●get_struct_val
・構造体管理番号
・識別子／序数
＞値
指定の構造体のメンバから値を取得します。
メンバはadd_structで指定した識別子か、先頭から何番目のメンバかという序数で指定します。
序数は1から始まります。

■型の名前
型は文字列で指定します。
型を指定する文字列は｀最長前方一致’で判断されます。
一覧にある文字列以外を後ろに付け足しても認識されます。
一覧にないものは「v」として扱われます。
なお、今のところ、constつきとそうでないものの区別はしていません。

文字列  型
v       void(返り値/引数無し)
i       32ビット符号付き整数
i8      8ビット符号付き整数
i16     16ビット符号付き整数
i64     64ビット符号付き整数
u       32ビット符号なし整数
u8      8ビット符号なし整数
u16     16ビット符号なし整数
u64     64ビット符号なし整数
r       64ビット浮動小数
r32     32ビット浮動小数
c       char
w       wchar_t
s       char*
uni     wchar_t*
cs      const char*
cu      const wchar_t*
p       ポインタ(アドレス)


■文でのサンプル
#define CALL_FUNC_SAORI 'call_func.dll'
// Win32APIのMessageBoxを呼ぶ
	// 関数を登録
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','user32.dll','MessageBoxA','i32','i32','cstr','cstr','i32')
	// 関数の呼び出し
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','MessageBoxA',0,'test1','test1',0)
	// 関数を削除
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','MessageBoxA')
	// 削除されているのでこの呼び出しは失敗する
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','MessageBoxA',0,'test1','test1',0)

// Win32APIのGetDCを呼び出す
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','user32.dll','GetDC','u32','u32')
	// GetDC(0)の返り値(デスクトップのデバイスコンテキスト)が返る
	_hdc = FUNCTIONEX(CALL_FUNC_SAORI,'call_func_ex','GetDC','user32.dll',0)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','GetDC','user32.dll)
	// HDC出力
	"%(_hdc)"

// Win32APIのGetLocalTimeを呼び出す
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','kernel32.dll','GetLocalTime','v','p')
	// メモリ確保
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_mem','p',16)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','GetLocalTime',_a)
	// メモリ先頭のWORD値を読む
	_year = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'u16')
	// メモリ先頭から2バイト先のu16値を読む
	_month = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,2,'u16')
	// メモリ先頭からu16値3つ分先ののu16値を読む
	_day = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,3,'u16','u16')
	// メモリ解放
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_mem',_a,'p')	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','GetLocalTime')
	// 日付出力
	"%(_year)/%(_month)/%(_day)"

// Win32APIのGetCurrentDirectoryを呼び出す
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','kernel32.dll','GetCurrentDirectoryA','u32','u32','ptr')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_mem','p',260)	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','GetCurrentDirectoryA',260,_a)
	_path = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'s')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_mem',_a,'p')	
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_func','GetCurrentDirectoryA')
	// パス出力
	"%(_path)"

// メモリに値を入れて別の型で取り出す
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_mem','u32',0x00018002)	
	// 下位のi16値を取り出す
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'i16')
	// 上位のu16値を取り出す
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,1,'u16','u16')
	// 下位にi16値を入れる
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_mem',-1,_a,'i16')
	// 上位にi16値を入れる
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_mem_ex',-2,_a,1,'i16','i16')
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem',_a,'u16')
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'get_mem_ex',_a,1,'u16','u16')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_mem',_a,'p')
	"%(_b)  %(_c)  %(_d)  %(_e)"

// 構造体利用例
	// 識別子を使わない
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','TEST','i32','i16','u32')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','TEST')
	// メンバをそれぞれ1,2,3で初期化
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val_all',_a,1,2,3)
	// 各メンバを序数によって読み書き
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,1)
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,2)
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,3)
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val',_a,2,100)
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,2)
	// 確保した構造体のメモリ領域を開放
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_struct',_a)
	// 構造体の登録情報を削除
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_struct','TEST')
	"%(_b)  %(_c)  %(_d)  %(_e)\n"
	--
	// 識別子を使う
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','TEST2','i32 abd','i16 ddd','u32 fds')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','TEST2')
	// メンバをそれぞれ1,2,3で初期化
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val_all',_a,1,2,3)
	// 各メンバを識別子によって読み書き
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'abd')
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'ddd')
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'fds')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val',_a,'ddd',100)
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_val',_a,'ddd')
	// 確保した構造体のメモリ領域を開放
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'free_struct',_a)
	// 構造体の登録情報を削除
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'remove_struct','TEST2')
	"%(_b)  %(_c)  %(_d)  %(_e)\n"

// CreateProcessを呼び出す
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_func','kernel32.dll','CreateProcessA','i32','cstr','str','p','p','i32','u32','p','p','p','p')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','STARTUPINFO','u32 cb','str','str','str','u32','u32','u32','u32','u32','u32','u32','u32','u16','u16','p','u32','u32','u32')
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'add_struct','PROCESS_INFORMATION','u32','u32','u32','u32')
	_a = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','STARTUPINFO')
	_b = FUNCTIONEX(CALL_FUNC_SAORI,'alloc_struct','PROCESS_INFORMATION')
	// 必要なメンバにだけ値を入れる
	_ = FUNCTIONEX(CALL_FUNC_SAORI,'set_struct_val',_a,'cb',68)
	_c = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_addr',_a)
	_d = FUNCTIONEX(CALL_FUNC_SAORI,'get_struct_addr',_b)
	_e = FUNCTIONEX(CALL_FUNC_SAORI,'call_func','CreateProcessA','C:\WINDOWS\SYSTEM32\CALC.EXE','',0,0,0,0,0,0,_c,_d)
	// 構造体から情報を取得
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

■謝辞
SAORIのフレームワークの作成/公開と作成に関するアドバイスを下さった芝やん氏に感謝します。


■ライセンス
NYSL Version 0.9982に従います。

http://www.kmonos.net/nysl/
NYSL Version 0.9982
----------------------------------------
A. 本ソフトウェアは Everyone'sWare です。このソフトを手にした一人一人が、
   ご自分の作ったものを扱うのと同じように、自由に利用することが出来ます。

  A-1. フリーウェアです。作者からは使用料等を要求しません。
  A-2. 有料無料や媒体の如何を問わず、自由に転載・再配布できます。
  A-3. いかなる種類の 改変・他プログラムでの利用 を行っても構いません。
  A-4. 変更したものや部分的に使用したものは、あなたのものになります。
       公開する場合は、あなたの名前の下で行って下さい。

B. このソフトを利用することによって生じた損害等について、作者は
   責任を負わないものとします。各自の責任においてご利用下さい。

C. 著作者人格権は しらまた(whiteball) に帰属します。著作権は放棄します。

D. 以上の３項は、ソース・実行バイナリの双方に適用されます。


■動作確認環境
WinXP SP3/Visual C++ 2005 Express Edition
SSP2.00.22+aya5で動作確認。


■連絡先
作者名・しらたま
サイト・JUNK ROOM
http://whiteball.m7.coreserver.jp/
メールアドレス
white_ball_11　hotmail.com
はてなダイアリー
http://d.hatena.ne.jp/white-ball/


■履歴
11/03/15    Ver.0.4    構造体関係のコマンドを追加(calc_offset,add_struct,remove_struct,alloc_struct,free_struct,get_struct_addr,set_struct_val_all,set_struct_val,get_struct_val)
09/03/07    Ver.0.3    alloc_memで初期値が省略できない不具合を修正
09/03/01    Ver.0.2    引数のない関数を呼び出そうとするとエラーになっていた不具合を修正
                       SAORIのあるフォルダにあるDLLを読み込めなかった不具合を修正
09/02/15    Ver.0.1    公開
