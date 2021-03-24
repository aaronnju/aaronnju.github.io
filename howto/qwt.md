
## 通用编译

```bash
wget https://nchc.dl.sourceforge.net/project/qwt/qwt/6.1.5/qwt-6.1.5.tar.bz2
tar -xvf qwt-6.1.5.tar.bz2
cd qwt-6.1.5/
vi qwtconfig.pri // disable #QWT_CONFIG     += QwtSvg
/usr/bin/qmake-qt5 qwt.pro
make
make install
```

## Mac下编译

```bash

# mac build qwt
cd ~/Source/qwt-6.1.5/  && /Users/shumingwang/Qt/5.12.0/clang_64/bin/qmake qwt.pro && make && sudo make install
sudo cp -r /usr/local/qwt-6.1.5/lib/qwt.framework  /Library/Frameworks/
```

## 修改统计图坐标轴文本为非科学技术
* ./qwt-6.1.5/src/qwt_abstract_scale_draw.cpp : 374
```C++
// old
QwtText QwtAbstractScaleDraw::label( double value ) const
{
    return QLocale().toString( value );
}
// new
QwtText QwtAbstractScaleDraw::label( double value ) const
{ 
    if (value > 100)
        return QLocale().toString( value , 'f', 0);
    else
        return QLocale().toString( value );
}
```
