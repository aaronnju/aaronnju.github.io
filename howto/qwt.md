
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
/Users/shumingwang/Qt/5.12.0/clang_64/bin/qmake qwt.pro
make
sudo make install
Inside your QT Project you have to add the following line to the .pro File include ( /usr/local/qwt-6.1.0/features/qwt.prf ) includes QWT libary into Project
Now you have to create a softlink like this : sudo ln -s /usr/local/qwt-6.1.0/lib/qwt.framework/qwt /usr/lib/qwt

## 修改统计图坐标轴文本为非科学技术
```C++
QwtText QwtAbstractScaleDraw::label( double value ) const
{
    return QLocale().toString( value , 'f', 0);
}
```
