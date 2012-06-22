#### Level 02 - Accessing secret information

We get the text "hvs doggkcfr bssrsr hc sbhsf hvwg gsqfsh rohopogs ct ucjsfbasbh gsqfshg wg pohhsfm - yssd hvs wbtcfaohwcb jsfm gsqfsh".

Looks like rot13, but It isn't. So let us try a script which runs rot 1 to 26...

```php
<?php
$string = 'hvs doggkcfr bssrsr hc sbhsf hvwg gsqfsh rohopogs ct ucjsfbasbh gsqfshg wg pohhsfm - yssd hvs wbtcfaohwcb jsfm gsqfsh';

function str_rot($s, $n = 13) { 
    $n = (int)$n % 26; 
    if (!$n) return $s; 
    for ($i = 0, $l = strlen($s); $i &lt; $l; $i++) { 
        $c = ord($s[$i]); 
        if ($c >= 97 && $c <= 122) { 
            $s[$i] = chr(($c - 71 + $n) % 26 + 97); 
        } else if ($c >= 65 && $c <= 90) { 
            $s[$i] = chr(($c - 39 + $n) % 26 + 65); 
        } 
    } 
    return $s; 
}

for ($i = 1; $i < 26; $i++) {
    print "($i) " . str_rot($string, $i) . "\n\n";
}
?>
```

Output:
```
user@ubuntu:~/Desktop$ php sadf.php 
(1) iwt ephhldgs cttsts id tcitg iwxh htrgti spipqpht du vdktgcbtci htrgtih xh qpiitgn - ztte iwt xcudgbpixdc ktgn htrgti
(2) jxu fqiimeht duutut je udjuh jxyi iushuj tqjqrqiu ev weluhdcudj iushuji yi rqjjuho - auuf jxu ydvehcqjyed luho iushuj
(3) kyv grjjnfiu evvuvu kf vekvi kyzj jvtivk urkrsrjv fw xfmviedvek jvtivkj zj srkkvip - bvvg kyv zewfidrkzfe mvip jvtivk
(4) lzw hskkogjv fwwvwv lg wflwj lzak kwujwl vslstskw gx ygnwjfewfl kwujwlk ak tsllwjq - cwwh lzw afxgjeslagf nwjq kwujwl
(5) max itllphkw gxxwxw mh xgmxk mabl lxvkxm wtmtutlx hy zhoxkgfxgm lxvkxml bl utmmxkr - dxxi max bgyhkftmbhg oxkr lxvkxm
(6) nby jummqilx hyyxyx ni yhnyl nbcm mywlyn xunuvumy iz aipylhgyhn mywlynm cm vunnyls - eyyj nby chzilguncih pyls mywlyn
(7) ocz kvnnrjmy izzyzy oj ziozm ocdn nzxmzo yvovwvnz ja bjqzmihzio nzxmzon dn wvoozmt - fzzk ocz diajmhvodji qzmt nzxmzo
(8) pda lwoosknz jaazaz pk ajpan pdeo oaynap zwpwxwoa kb ckranjiajp oaynapo eo xwppanu - gaal pda ejbkniwpekj ranu oaynap
(9) qeb mxpptloa kbbaba ql bkqbo qefp pbzobq axqxyxpb lc dlsbokjbkq pbzobqp fp yxqqbov - hbbm qeb fkclojxqflk sbov pbzobq
(10) rfc nyqqumpb lccbcb rm clrcp rfgq qcapcr byryzyqc md emtcplkclr qcapcrq gq zyrrcpw - iccn rfc gldmpkyrgml tcpw qcapcr
(11) sgd ozrrvnqc mddcdc sn dmsdq sghr rdbqds czszazrd ne fnudqmldms rdbqdsr hr azssdqx - jddo sgd hmenqlzshnm udqx rdbqds
(12) the password needed to enter this secret database of government secrets is battery - keep the information very secret
(13) uif qbttxpse offefe up foufs uijt tfdsfu ebubcbtf pg hpwfsonfou tfdsfut jt cbuufsz - lffq uif jogpsnbujpo wfsz tfdsfu
(14) vjg rcuuyqtf pggfgf vq gpvgt vjku ugetgv fcvcdcug qh iqxgtpogpv ugetgvu ku dcvvgta - mggr vjg kphqtocvkqp xgta ugetgv
(15) wkh sdvvzrug qhhghg wr hqwhu wklv vhfuhw gdwdedvh ri jryhuqphqw vhfuhwv lv edwwhub - nhhs wkh lqirupdwlrq yhub vhfuhw
(16) xli tewwasvh riihih xs irxiv xlmw wigvix hexefewi sj kszivrqirx wigvixw mw fexxivc - oiit xli mrjsvqexmsr zivc wigvix
(17) ymj ufxxbtwi sjjiji yt jsyjw ymnx xjhwjy ifyfgfxj tk ltajwsrjsy xjhwjyx nx gfyyjwd - pjju ymj nsktwrfynts ajwd xjhwjy
(18) znk vgyycuxj tkkjkj zu ktzkx znoy ykixkz jgzghgyk ul mubkxtsktz ykixkzy oy hgzzkxe - qkkv znk otluxsgzout bkxe ykixkz
(19) aol whzzdvyk ullklk av lualy aopz zljyla khahihzl vm nvclyutlua zljylaz pz ihaalyf - rllw aol pumvythapvu clyf zljyla
(20) bpm xiaaewzl vmmlml bw mvbmz bpqa amkzmb libijiam wn owdmzvumvb amkzmba qa jibbmzg - smmx bpm qvnwzuibqwv dmzg amkzmb
(21) cqn yjbbfxam wnnmnm cx nwcna cqrb bnlanc mjcjkjbn xo pxenawvnwc bnlancb rb kjccnah - tnny cqn rwoxavjcrxw enah bnlanc
(22) dro zkccgybn xoonon dy oxdob drsc combod nkdklkco yp qyfobxwoxd combodc sc lkddobi - uooz dro sxpybwkdsyx fobi combod
(23) esp alddhzco yppopo ez pyepc estd dpncpe olelmldp zq rzgpcyxpye dpncped td mleepcj - vppa esp tyqzcxletzy gpcj dpncpe
(24) ftq bmeeiadp zqqpqp fa qzfqd ftue eqodqf pmfmnmeq ar sahqdzyqzf eqodqfe ue nmffqdk - wqqb ftq uzradymfuaz hqdk eqodqf
(25) gur cnffjbeq arrqrq gb ragre guvf frperg qngnonfr bs tbireazrag frpergf vf onggrel - xrrc gur vasbezngvba irel frperg
```

Looks like rot12 to me ;>