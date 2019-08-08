function xqhs()
{
    chuci = 1;
    bfbz = 1;
    ++p;
    if (p == yinyue.length)
    {
        p = 0;
    } // end if
    gofun();
    shouyea.anzh.bofang._visible = 0;
    shouyea.anzh.zanting._visible = 1;
    _root.play_BG.loadMusicPlay.gotoAndPlay(2);
    _root.play_BG.loadMusicPlay.BNT.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY1.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY2.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY3.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY4.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY5.gotoAndPlay("start");
    _root.BNT2.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.mix.gotoAndStop(1);
} // End of the function
function gofun()
{
    zhuanjijs = int(p / 16);
    if (zhuanjijs <= 18)
    {
        if (!_root.dakaigc)
        {
            shouyea.anzh.gotoAndStop(1);
        }
        else
        {
            shouyea.anzh.gotoAndStop(2);
        } // end else if
    }
    else
    {
        shouyea.anzh.gotoAndStop(3);
    } // end else if
    ls = zhuanjijs + 1;
    tuwen.gotoAndStop(ls);
    zjlb.dg.zddqbf();
    xqml.dg.zddqbf();
    shouyea.jsq = shouyea.zd + 1;
    shouyea.zhtjs = 0;
    shouyea.sjxs = "00:00 | 00:00";
    shouyea.shouyeagm.k = 98;
    geci.gccz.dqgc = gchs + gqmingchen[p];
    geci.gccz.geci = gchs + "\r";
    geci.gccz.gcwb.scroll = 0;
    mymusic.stop();
    mymusic = new Sound();
    mymusic.loadSound(yinyue[p], true);
    if (gclrc[p] == undefined)
    {
        gcxsyn = 0;
    }
    else
    {
        if (geci.gcsp._visible != 1)
        {
            geci.spgm = "";
        }
        else
        {
            geci.spgm = gqmingchen[p];
        } // end else if
        geci.gcsp.gcwb.gcwb.text = "";
        geci.gcsp.gcwbf.gcwb.text = "";
        geci.gcsp.gcwb1.gcwb.text = "";
        geci.gcsp.gcwb2.gcwb.text = "";
        gcxsyn = 1;
        gcjs = 0;
        gcfl(p);
        gcbf();
    } // end else if
    if (!chuci)
    {
        mymusic.setVolume(0);
    }
    else
    {
        mymusic.setVolume(100);
    } // end else if
    mymusic.onSoundComplete = function ()
    {
        ++p;
        if (p == yinyue.length)
        {
            p = 0;
        } // end if
        geci.gccz.gcwb.scroll = 0;
        geci.gccz.dqgc = gchs + gqmingchen[p];
        geci.gccz.geci = gchs + "\r";
        gofun();
    };
} // End of the function
function gcfl(gqs)
{
    delete gcmingchen;
    delete gcbiaoti;
    gcmingchen = new Array();
    gcbiaoti = new Array();
    lrc = _root.gclrc[gqs];
    sjpyl = 0;
    gcmingchen.splice(1);
    gcbiaoti.splice(1);
    a = -1;
    biaoti = 0;
    hcwz = 1;
    c3 = 0;
    for (i = 0; hcwz > 0; i++)
    {
        a = lrc.indexOf("[", a + 1);
        c2 = a;
        hcwz11 = a;
        hcwz = lrc.indexOf("\r", a);
        yhgc = lrc.slice(a, hcwz);
        if (c2 > c3 || i == 0)
        {
            wb = wb + yhgc + "\r";
            c3 = hcwz;
        } // end if
        c1 = a;
        if (hcwz == -1)
        {
            yhgc = lrc.slice(a);
        } // end if
        yhgccd = length(yhgc);
        zhkh = yhgc.lastIndexOf("]");
        if (hcwz != -1)
        {
            gcwz = yhgc.slice(zhkh + 1, hcwz);
        }
        else
        {
            gcwz = yhgc.slice(zhkh + 1);
        } // end else if
        if (yhgccd == zhkh + 1)
        {
            aa = yhgc.slice(1, 3);
            if (aa == "ti")
            {
                cc = yhgc.indexOf("]");
                bb = "歌曲：" + yhgc.slice(4, cc);
                gcbiaoti[biaoti] = bb;
                this["xs" + biaoti] = gcbiaoti[biaoti];
            } // end if
            if (aa == "ar")
            {
                cc = yhgc.indexOf("]");
                bb = "演唱：" + yhgc.slice(4, cc);
                gcbiaoti[biaoti] = bb;
                this["xs" + biaoti] = gcbiaoti[biaoti];
            } // end if
            if (aa == "al")
            {
                cc = yhgc.indexOf("]");
                bb = "专辑：" + yhgc.slice(4, cc);
                gcbiaoti[biaoti] = bb;
                this["xs" + biaoti] = gcbiaoti[biaoti];
            } // end if
            if (aa == "by")
            {
                cc = yhgc.indexOf("]");
                bb = "编辑：" + yhgc.slice(4, cc);
                cc1 = yhgc.indexOf("-");
                ++cc1;
                tppt = yhgc.slice(cc1, cc);
                gcbiaoti[biaoti] = bb;
                this["xs" + biaoti] = gcbiaoti[biaoti];
            } // end if
            if (aa == "of")
            {
                cc = yhgc.indexOf("]");
                bb = yhgc.slice(8, cc);
                sjpyl = Number(bb);
            } // end if
            ++biaoti;
        }
        else
        {
            ykhwz = yhgc.indexOf("]", 0) + 1;
            gcmingchen[i] = yhgc.slice(0, ykhwz) + gcwz;
        } // end else if
        if (hcwz11 == -1)
        {
            hcwz = -1;
        } // end if
    } // end of for
    gcmingchen.sort();
    geci.gccz.geci = gchs + "\r";
    for (i = 0; i < gcmingchen.length; i++)
    {
        if (gcmingchen[i].slice(ykhwz))
        {
            geci.gccz.geci = geci.gccz.geci + gcmingchen[i].slice(ykhwz) + "\r";
        } // end if
    } // end of for
    for (i = 0; i < 13; i++)
    {
        geci.gccz.geci = geci.gccz.geci + "\r";
    } // end of for
} // End of the function
function gcbf()
{
    gcwbw = gcwbx = gcw / 2;
    gctmdbz = 0;
    geci.gcsp.gcwb._x = gcw / 2;
    geci.gcsp.gcwb1._x = gcw / 2 - 2500;
    geci.gcsp.gcwb2._x = gcw / 2;
    geci.gcsp.gcwb1.gcwb.text = "";
    geci.gcsp.gcwbf.gcwb.text = "";
    geci.gcsp.gcwb1.gcwb.text = "";
    geci.gcsp.gcwb2.gcwb.text = "";
    gc.onEnterFrame = function ()
    {
        sj1 = Number(gcmingchen[gcjs].slice(1, 3));
        sj2 = Number(gcmingchen[gcjs].slice(4, 6));
        kk = gcmingchen[gcjs].indexOf("]", 0);
        if (kk != 9)
        {
            sj3 = 0;
        }
        else
        {
            sj3 = Number(gcmingchen[gcjs].slice(7, 9));
        } // end else if
        sycd = mymusic.duration;
        sybf = mymusic.position;
        shijian(sycd);
        sjxs = time;
        shijian(sybf);
        shouyea.sjxs = sjxs + " | " + time;
        sj = (sj1 * 60 + sj2) * 1000 + sj3;
        sj1 = Number(gcmingchen[gcjs + 1].slice(1, 3));
        sj2 = Number(gcmingchen[gcjs + 1].slice(4, 6));
        kk = gcmingchen[gcjs + 1].indexOf("]", 0);
        if (kk != 9)
        {
            sj3 = 0;
        }
        else
        {
            sj3 = Number(gcmingchen[gcjs + 1].slice(7, 9));
        } // end else if
        sja = (sj1 * 60 + sj2) * 1000 + sj3;
        gcjs1 = gcjs;
        gcsjjs = sj + sjpyl;
        gcphyd();
        if (gcsjjs < sybf && bfbz == 1 && gcbfbz == 1)
        {
            geci.spgm = "";
            sybf1 = sybf;
            geci.gccz.gcwb._y = geci.gccz.gcwb1._y = gcgdy;
            geci.gccz.dqgc = gchs;
            geci.gccz.dqgc = geci.gccz.dqgc + gcmingchen[gcjs].slice(ykhwz);
            ++geci.gccz.gcwb.scroll;
            geci.gcsp.gcwb._x = gcwbx - gcwbw;
            ls = gcmingchen[gcjs].slice(ykhwz);
            zishu = ls.length;
            for (i = 0; i < ls.length; i++)
            {
                if (ls.charCodeAt(i) < 1000)
                {
                    zishu = zishu - 5.000000E-001;
                } // end if
            } // end of for
            if (ls == undefined)
            {
                geci.gcsp.gcwb.artist = geci.gcsp.gcwbf.artist = "";
            }
            else
            {
                geci.gcsp.gcwb.artist = geci.gcsp.gcwbf.artist = ls;
            } // end else if
            geci.gcsp.gcwb._x = geci.gcsp.gcwbf._x = gcwbx = gcw / 2;
            gcwbw = (zishu + 1) * (Number(gczh) + 0);
            geci.gcsp.gcwb._alpha = 0;
            geci.gcsp.gcwbf._alpha = Number(gcdqtm);
            gctmdbz = 1;
            yd = gcwbw / ((sja - sj) / 1000 * 12);
            geci.gcsp.gcwb1.artist = "";
            geci.gcsp.gcwb1._x = gcwb1x = -2500 + gcw / 2;
            gczuhe(gcjs - 3);
            gczuhe(gcjs - 2);
            gczuhe(gcjs - 1);
            geci.gcsp.gcwb2.artist = "";
            gczuhe1(gcjs + 1);
            gczuhe1(gcjs + 2);
            gczuhe1(gcjs + 3);
            gczuhe1(gcjs + 4);
            geci.gcsp.gcwb2._x = gcwb2x = gcwbx + gcwbw;
            ++gcjs;
        } // end if
    };
} // End of the function
function gcphyd()
{
    yhgd = geci.gccz.gcwb._height / gczhs;
    ydxs = yhgd / (gcsjjs - sybf1) * (sybf - sybf1);
    if (gcydbz && sybf > 1)
    {
        geci.gccz.gcwb._y = geci.gccz.gcwb1._y = gcgdy - ydxs;
    } // end if
} // End of the function
function gczuhe(gciscs)
{
    ls = gcmingchen[gciscs].slice(ykhwz);
    if (ls == undefined)
    {
        ls1 = "";
    }
    else
    {
        ls1 = ls;
    } // end else if
    geci.gcsp.gcwb1.artist = geci.gcsp.gcwb1.artist + ls1 + "　";
} // End of the function
function gczuhe1(gciscs)
{
    ls = gcmingchen[gciscs].slice(ykhwz);
    if (ls == undefined)
    {
        ls1 = "";
    }
    else
    {
        ls1 = ls;
    } // end else if
    geci.gcsp.gcwb2.artist = geci.gcsp.gcwb2.artist + ls1 + "　";
} // End of the function
function shijian(cs_sj)
{
    var _loc4 = cs_sj;
    var _loc3 = _loc4 / 1000;
    var _loc1 = Math.floor(_loc3 / 60);
    if (_loc1 >= 10)
    {
        _loc5 = String(_loc1);
    }
    else
    {
        _loc5 = "0" + _loc1;
    } // end else if
    var _loc2 = Math.round(_loc3 - _loc1 * 60);
    if (_loc2 < 10)
    {
        _loc2 = "0" + _loc2;
    } // end if
    time = _loc5 + ":" + _loc2;
} // End of the function
function oSzxz1()
{
    yinyue[p] = _root.mp3txt0[p];
    gofun();
} // End of the function
function oSzxz2()
{
    yinyue[p] = _root.mp3txt1[p];
    gofun();
} // End of the function
function oSzxz3()
{
    ls = p % 16 + 1;
    if (ls >= 10)
    {
        sl = ls;
    }
    else
    {
        sl = "0" + ls;
    } // end else if
    gkdz = gktym + gkzjm[zhuanjijs] + "/gk" + (zhuanjijs + 1) + sl + ".mp3";
    yinyue[p] = gkdz;
    gofun();
} // End of the function
stop ();
stop ();
_root.S._visible = 0;
_root.X._visible = 0;
stop ();
yp._x = yp1x + 5;
yp._y = yp1y + 12;
yp._xscale = 95;
yp._yscale = 100;
mysound = new Sound();
yymc._visible = 0;
laba._visible = 0;
sckz._visible = 0;
_root.kedie_mc._visible = 0;
_root.kedie_mc._visible = 0;
_root.zjlb._visible = 0;
_root.tuwen._visible = 0;
gczt = "_sans";
gczh = "14";
gckd = "300";
gcgd = "300";
gcys = "F7F7F7";
gcdqys = "E9EF40";
gcdqhs = "6";
gczhs = "14";
gcw = "400";
gcbfys = "E9EF40";
gcdbfys = "1E6CBB";
gcdqtm = "100";
dgx = "-8";
dgy = "33";
xqml.dg._x = zjlb.dg._x = dgx == undefined ? (20) : (Number(dgx));
xqml.dg._y = zjlb.dg._y = dgy == undefined ? (20) : (Number(dgy));
dggd = "400";
mask_mc_height = dggd == undefined ? (200) : (Number(dggd));
dqwzys = "D9F4FF";
dqwzys = dqwzys == undefined ? (16711680) : (Number("0x" + dqwzys));
wzys = "D3D3D3";
_global.fontcolor = wzys == undefined ? (65280) : (Number("0x" + wzys));
_global.dgqmbj = dgqmbj == undefined ? (0) : (Number("0x" + dgqmbj));
xqml.dg.dgbj._alpha = zjlb.dg.dgbj._alpha = dgbjtm == undefined ? (0) : (Number(dgbjtm));
dgwzkd = "200";
_global.mask_mc_width = dgwzkd == undefined ? (200) : (Number(dgwzkd) + 20);
xqml.dg._visible = zjlb.dg._visible = 0;
gcbjtmd = gcbjtmd == undefined ? (0) : (Number(gcbjtmd));
gcbjys = gcbjys == undefined ? (16777215) : (Number("0x" + gcbjys));
bj._x = gcbjx == undefined ? (0) : (Number(gcbjx));
bj._y = gcbjy == undefined ? (0) : (Number(gcbjy));
bj._width = gcbjkd == undefined ? (550) : (Number(gcbjkd));
bj._height = gcbjgd == undefined ? (200) : (Number(gcbjgd));
var gcwb_fmt = new TextFormat();
gcwb_fmt.font = gczt == undefined ? ("宋体") : (gczt);
gcwb_fmt.leading = gchj == undefined ? (5) : (Number(gchj));
gcwb_fmt.size = gczh == undefined ? (16) : (Number(gczh));
gcwb_fmt.align = gcdq == undefined ? ("center") : (gcdq);
gcwb_fmt.bold = gcct == undefined ? (false) : (true);
gcwb_fmt.italic = gcxt == undefined ? (false) : (true);
geci.gccz.gcwb.setNewTextFormat(gcwb_fmt);
geci.gccz.gcwb1.setNewTextFormat(gcwb_fmt);
var gcwb_fmt1 = new TextFormat();
gcwb_fmt1.font = gczt == undefined ? ("宋体") : (gczt);
gcwb_fmt1.leading = gchj == undefined ? (5) : (Number(gchj));
gcwb_fmt1.size = gczh == undefined ? (16) : (Number(gczh));
gcwb_fmt1.bold = gcct == undefined ? (false) : (true);
gcwb_fmt1.italic = gcxt == undefined ? (false) : (true);
geci.gcsp.gcwb.gcwb.setNewTextFormat(gcwb_fmt1);
geci.gcsp.gcwbf.gcwb.setNewTextFormat(gcwb_fmt1);
geci.gcsp.gcwb1.gcwb.setNewTextFormat(gcwb_fmt1);
geci.gcsp.gcwb2.gcwb.setNewTextFormat(gcwb_fmt1);
geci.gccz.gcwb._width = geci.gccz.gcwb1._width = gckd == undefined ? (550) : (Number(gckd));
geci.gccz.gcwb._height = geci.gccz.gcwb1._height = gcgd == undefined ? (200) : (Number(gcgd));
geci.gccz.gcwb._x = geci.gccz.gcwb1._x = 0;
geci.gccz.gcwb._y = geci.gccz.gcwb1._y = 0;
geci.gccz.gcwb.textColor = gcys == undefined ? (0) : (Number("0x" + gcys));
geci.gccz.gcwb1.textColor = gcdqys == undefined ? (16711680) : (Number("0x" + gcdqys));
gcdqhs = gcdqhs == undefined ? (5) : (Number(gcdqhs));
gczhs = gczhs == undefined ? (11) : (Number(gczhs));
geci.gcsp.gcwb.gcwb.textColor = Number(gcys);
gcbfys = gcbfys == undefined ? ("0xff0000") : ("0x" + gcbfys);
geci.gcsp.gcwb.gcwb.textColor = Number(gcbfys);
gcdbfys = gcdbfys == undefined ? ("0x000000") : ("0x" + gcdbfys);
geci.gcsp.gcwbf.gcwb.textColor = Number(gcdbfys);
geci.gcsp.gcwb1.gcwb.textColor = Number(gcdbfys);
geci.gcsp.gcwb2.gcwb.textColor = Number(gcdbfys);
gcdqtm = gcdqtm == undefined ? ("70") : (gcdqtm);
geci.gcsp.gcwbf.gcwb._alpha = Number(gcdqtm);
geci.gcsp.gcwb1.gcwb._alpha = Number(gcdqtm);
geci.gcsp.gcwb2.gcwb._alpha = Number(gcdqtm);
gchs = "";
for (i = 0; i < gcdqhs - 1; i++)
{
    gchs = gchs + "\r";
} // end of for
gcys1 = gcys1 == undefined ? ("") : ("0x" + gcys1);
if (gcys1 != "")
{
    var glow = new flash.filters.GlowFilter(Number(gcys1), 1, 4, 4);
    geci.gccz.gcwb.gcwb.filters = [glow];
    geci.gcsp.gcwb.gcwb.filters = [glow];
    geci.gcsp.gcwbf.gcwb.filters = [glow];
    geci.gcsp.gcwb1.gcwb.filters = [glow];
    geci.gcsp.gcwb2.gcwb.filters = [glow];
} // end if
gcw = gcw == undefined ? (690) : (Number(gcw));
_root.gcbfbz = true;
var yinyue = new Array();
gcmingchen = new Array();
gcbiaoti = new Array();
gqmingchen = new Array();
gclrc = new Array();
_root.dakaigc = 0;
shouyea.anzh.bofang._visible = 0;
shouyea.anzh.tingzhi._visible = 0;
shouyea.anzh.shangqu._visible = 0;
shouyea.anzh.xiaqu._visible = 0;
shouyea.anzh.zanting._visible = 0;
var fengefu = "|";
gkzjm = gkmp3.split(fengefu);
mp3gc = "http://aimg8.dlszywz.com/ueditor/file/520/1039950/1479722720948514.txt";
var lrctxt = new LoadVars();
lrctxt.onData = function (src)
{
    if (src != undefined)
    {
        qblrc = src;
        var _loc3 = "#ks#";
        gclrc = src.split(_loc3);
        var _loc1 = 0;
        while (_loc1 < gclrc.length)
        {
            a = gclrc[_loc1].indexOf("ti:", 1);
            hcwz = gclrc[_loc1].indexOf("]", a);
            b = _loc1 + 1;
            yhgc = b + "." + gclrc[_loc1].slice(a + 3, hcwz);
            gqmingchen[_loc1] = yhgc;
            a = gclrc[_loc1].indexOf("ur", 1);
            hcwz = gclrc[_loc1].indexOf("]", a);
            yhgc = gclrc[_loc1].slice(a + 4, hcwz);
            yinyue[_loc1] = yhgc;
            ++_loc1;
        } // end while
        shouyea.anzh.bofang._visible = 1;
        shouyea.anzh.tingzhi._visible = 1;
        shouyea.anzh.shangqu._visible = 1;
        shouyea.anzh.xiaqu._visible = 1;
        xqml.dg._visible = zjlb.dg._visible = 1;
        xqml.dg.dg.dgmcxz();
        zjlb.dg.dg.dgmcxz();
        p = random(yinyue.length);
        zhuanjijs = int(p / 16);
        zjlb.dg.zddqbf();
        geci.gccz.dqgc = gchs + gqmingchen[p];
    } // end if
};
lrctxt.load(mp3gc);
pausetime = 0;
gcydbz = 1;
geci.gcsp.gcwb._width = gcw;
geci.gcsp.gcwb._x = (gcw - gqmingchen[p].length * Number(gczh)) / 2;
geci.gcsp.gcwb1.gcwb._width = 2500;
geci.gcsp.gcwb2.gcwb._width = 2500;
chuci = 0;
bfbz = 0;
geci.gccz._visible = 1;
geci.gcsp._visible = 0;
pausetime = 0;
oSxz = 0;
oSxzz = 0;
this.onEnterFrame = function ()
{
    if (gctmdbz == 1)
    {
        _root.geci.gcsp.gcwb._alpha = _root.geci.gcsp.gcwb._alpha + 5;
    } // end if
    if (_root.bfbz)
    {
        if (_root.gcwbx - _root.geci.gcsp.gcwb._x + 5 < _root.gcwbw)
        {
            --geci.gcsp.gcwbf._alpha;
            _root.geci.gcsp.gcwb._x = _root.geci.gcsp.gcwb._x - _root.yd;
            _root.geci.gcsp.gcwbf._x = _root.geci.gcsp.gcwbf._x - _root.yd;
            _root.geci.gcsp.gcwb1._x = _root.geci.gcsp.gcwb1._x - _root.yd;
            _root.geci.gcsp.gcwb2._x = _root.geci.gcsp.gcwb2._x - _root.yd;
        } // end if
    } // end if
    if (!((mymusic.position < 1 || mymusic.duration < 1) && chuci))
    {
        oSxz = 0;
        oSxzz = 0;
    }
    else
    {
        ++oSxz;
        if (oSxz == 100)
        {
            ++oSxzz;
            oSxz = 0;
            switch (oSxzz)
            {
                case 1:
                {
                    oSzxz1();
                    break;
                } 
                case 2:
                {
                    oSzxz2();
                    break;
                } 
                case 3:
                {
                    oSzxz3();
                    break;
                } 
                default:
                {
                    oSxzz = 0;
                    xqhs();
                    break;
                } 
            } // End of switch
        } // end if
    } // end else if
};
shouyea.anzh.bofang.onRelease = function ()
{
    chuci = 1;
    gcydbz = 1;
    bfbz = 1;
    if (!pausetime)
    {
        gofun();
    }
    else
    {
        mymusic.start(pausetime);
    } // end else if
    shouyea.anzh.bofang._visible = 0;
    shouyea.anzh.zanting._visible = 1;
    _root.play_BG.loadMusicPlay.gotoAndPlay(2);
    _root.play_BG.loadMusicPlay.BNT.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY1.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY2.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY3.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY4.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.PY5.gotoAndPlay("start");
    _root.BNT2.gotoAndPlay("start");
    _root.play_BG.loadMusicPlay.mix.gotoAndStop(1);
    mymusic.setVolume(100);
};
shouyea.anzh.zanting.onRelease = function ()
{
    gcydbz = 0;
    bfbz = 0;
    mymusic.stop();
    pausetime = mymusic.position / 1000;
    shouyea.anzh.bofang._visible = 1;
    shouyea.anzh.zanting._visible = 0;
    _root.play_BG.loadMusicPlay.gotoAndPlay(1);
    _root.play_BG.loadMusicPlay.BNT.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY1.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY2.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY3.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY4.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY5.gotoAndPlay("Ttart");
    _root.BNT2.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.mix.gotoAndStop(2);
};
shouyea.anzh.tingzhi.onRelease = function ()
{
    bfbz = 0;
    mymusic.stop();
    pausetime = 0;
    shouyea.anzh.bofang._visible = 1;
    shouyea.anzh.zanting._visible = 0;
    _root.play_BG.loadMusicPlay.gotoAndPlay(1);
    _root.play_BG.loadMusicPlay.BNT.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY1.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY2.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY3.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY4.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.PY5.gotoAndPlay("Ttart");
    _root.BNT2.gotoAndPlay("Ttart");
    _root.play_BG.loadMusicPlay.mix.gotoAndStop(2);
};
shouyea.anzh.shangqu.onRelease = function ()
{
    chuci = 1;
    bfbz = 1;
    --p;
    if (p < 0)
    {
        p = yinyue.length - 1;
    } // end if
    gofun();
    shouyea.anzh.bofang._visible = 0;
    shouyea.anzh.zanting._visible = 1;
    _root.play_BG.loadMusicPlay.gotoAndPlay(2);
    _root.play_BG.loadMusicPlay.mix.gotoAndStop(1);
};
shouyea.anzh.xiaqu.onRelease = function ()
{
    xqhs();
};
gcgdy = geci.gccz.gcwb._y;
ae._visible = true;
bt._visible = false;
ae.onRelease = function ()
{
    yp._visible = false;
    xqml._visible = 1;
    ae._visible = false;
    bt._visible = true;
    flvmc = "打开菜单";
    kkk._visible = true;
};
bt.onRelease = function ()
{
    loadMovie("http://aimg8.dlszywz.com/ueditor/file/520/1039950/1479801685863704.swf ", yp);
    yp._xscale = 115;
    yp._yscale = 65;
    yp._visible = true;
    bt._visible = false;
    ae._visible = true;
    flvmc = "关闭菜单";
    kkk._visible = false;
    xqml._visible = 0;
};
