
# デフォルト動作

default :
	../z_tools/make.exe run

# ファイル生成規則

renren.bin : abc.nas Makefile
	../z_tools/nask.exe abc.nas renren.bin renren.lst

renren.img : renren.bin Makefile
	../z_tools/edimg.exe imgin:../z_tools/fdimg0at.tek \
                   wbinimg src:renren.bin len:512 from:0 to:0 imgout:renren.img

#	コマンド

asm :
	../z_tools/make.exe -r renren.bin

img :
	../z_tools/make.exe -r renren.img

run :
	../z_tools/make.exe img
	copy renren.img ..\z_tools\qemu\fdimage0.bin
	../z_tools/make.exe -C ../z_tools/qemu

install :
	../z_tools/make.exe img
	../z_tools/imgtol.com w a: renren.img

clean :
	-del renren.bin
	-del renren.lst

src_only :
	../z_tools/make.exe sclean
	-del renren.img