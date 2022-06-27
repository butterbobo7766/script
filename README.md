gg["alert"]("      🐮 [掛狗] の Bᴜᴛᴛᴇʀ 🐮\n\n🌸 [啟動劇本] 🌷 [Enter Script] 🌸")
gg["toast"]("⚠️ 請小心使用 ⚠️")

---- Progress ----
gg.setVisible(false)
gg.sleep(100) gg.toast("║▓░░░░░░░░░░░░░░║") gg.sleep(100) gg.toast("║▓▓▓░░░░░░░░░░░░║") gg.sleep(100) gg.toast("║▓▓▓▓▓░░░░░░░░░░║") gg.sleep(100) gg.toast("║▓▓▓▓▓▓░░░░░░░░░║") gg.sleep(100) gg.toast("║▓▓▓▓▓▓▓░░░░░░░░║") gg.sleep(100) gg.toast("║▓▓▓▓▓▓▓▓▓░░░░░░║") gg.sleep(100) gg.toast("║▓▓▓▓▓▓▓▓▓▓▓▓░░░║") gg.sleep(100) gg.toast("║▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓║")
gg.setVisible(false)

---- Use Codes ----
CA=gg.REGION_C_ALLOC  VI=gg.REGION_VIDEO  XA=gg.REGION_CODE_APP  AN=gg.REGION_ANONYMOUS  CD=gg.REGION_C_DATA  BSS=gg.REGION_C_BSS  EA=gg.editAll  RL=gg.getRangesList  SN=gg.searchNumber  GR=gg.getResults  SET=gg.setVisible  REFINE=gg.refineNumber  COUNT=gg.getResultCount  RANGE=gg.setRanges  XOR=gg.TYPE_XOR  BYTE=gg.TYPE_BYTE  FLOAT=gg.TYPE_FLOAT  WORD=gg.TYPE_WORD  DWORD=gg.TYPE_DWORD  DOUBLE=gg.TYPE_DOUBLE  QWORD=gg.TYPE_QWORD function setvalue(address, flags, value) local tt = {} tt[1] = {} tt[1].address = address tt[1].flags = flags tt[1].value = value gg.setValues(tt) end local Hex = {} function patch(lib, offset, edit, type) local ranges = gg.getRangesList(lib) local xy = {} xy[1] = {} xy[1].address = ranges[1].start + offset xy[1].flags = type xy[1].value = edit gg.setValues(xy) end local HexPatches = {} function HexPatches.MemoryPatch(Lib, Offset, Edit, Type) local Ranges = gg.getRangesList(Lib) local v = {} v[1] = {} v[1].address = Ranges[1].start + Offset v[1].flags = Type v[1].value = Edit.."r" v[1].freeze = true gg.setValues(v) end function AxM(Search, Write, Type) gg.clearResults() gg.setVisible(false) gg.searchNumber(Search[1][1], Type) local count = gg.getResultCount() local result = gg.getResults(count) gg.clearResults() local data = {} local base = Search[1][2] if (count > 0) then for i, v in ipairs(result) do v.isUseful = true end for k=2, #Search do local tmp = {} local offset = Search[k][2] - base local num = Search[k][1] for i, v in ipairs(result) do tmp[#tmp+1] = {} tmp[#tmp].address = v.address + offset tmp[#tmp].flags = v.flags end tmp = gg.getValues(tmp) for i, v in ipairs(tmp) do if ( tostring(v.value) ~= tostring(num) ) then result[i].isUseful = false end end end for i, v in ipairs(result) do if (v.isUseful) then data[#data+1] = v.address end end if (#data > 0) then gg.toast("🐮 ʀᴇsᴜʟᴛs ( "..#data.." ) ᴄʜᴀɴɢᴇ 🐮") local t = {} local base = Search[1][2] for i=1, #data do for k, w in ipairs(Write) do offset = w[2] - base t[#t+1] = {} t[#t].address = data[i] + offset t[#t].flags = Type t[#t].value = w[1] if (w[3] == true) then local item = {} item[#item+1] = t[#t] item[#item].freeze = true gg.addListItems(item) end end end gg.setValues(t) gg.toast("🐮 ʀᴇsᴜʟᴛs ( "..#t.." ) ᴄʜᴀɴɢᴇ 🐮") gg.addListItems(t) else gg.toast("🐮 ᴅᴀᴛᴀ ɴᴏᴛ ғᴏᴜɴᴅ 🐮", false) return false end else gg.toast("🐮 ᴅᴀᴛᴀ ɴᴏᴛ ғᴏᴜɴᴅ 🐮") return false end end

gg["setVisible"](true)
---- Script Body ----
function Main()
menu = gg["multiChoice"]({
    "° [ᴛɪᴍɪ [ʟᴏɢᴏ] ʙʏᴘᴀss] °", ---a1
    "° [Bʏᴘᴀss *ɪɴ* Lᴏʙʙʏ] °", ---b1
    "° [ʙʟᴜᴇ ᴀɴᴛʜᴇɴᴀ] 藍色天線 °", ---c1
    "° [ᴇsᴘ ɴᴀᴍᴇ ʙʀ] 顯示人名 °️", ---d1
    "° [ᴍᴀɢɪᴄ ʙᴜʟʟᴇᴛ] 生存魔術彈 °", ---e1
    "° [ғᴀsᴛ ʀᴜɴ x15] 高跑速 x15 °", ---f1
    "° [ғʟᴀsʜ ʀᴜɴ x5] 跑速 x5 °️", ---g1
    "° [sᴘᴇᴇᴅ ʀᴜɴ x3] 微加速 x3 °", ---h1
    "° [ᴡᴀʟʟнᴀᴄᴋ] 透視敵人 °", ---i1
    "° [ᴀɪᴍʙᴏᴛ] 瞄準輔助 °", ---j1
    "° [ᴀɪᴍʟᴏᴄᴋ] 開火鎖定 °️", ---k1
    "° [ғᴀsᴛ sᴄᴏᴘᴇ] 秒開鏡 °", ---l1
    "° [ѕмall croѕѕнaιr] 縮小準星 °", ---m1
    "° [ɴᴏ ʀᴇᴄᴏɪʟ] 減後座力 °", ---n1
    "° [ғᴀsᴛ ʀᴇʟᴏᴀᴅ] 快速上彈 °", ---o1
    "°️ [ɴᴏ sᴘʀᴇᴀᴅ] 無散發 °️", ---p1
    "°️ [ʀᴀᴅᴀʀ ʜᴀᴄᴋ] 地圖長顯 °️", ---q1
    "° [No Parachute] 秒落地 °", ---r1
    "° [ғᴀsᴛsʜσσᴛ]️ 增強射速 °", ---s1
    "° [ᴍᴀɢɪᴄ ʙᴜʟʟᴇᴛ] 魔術彈80% °", ---t1
    "° [ʙᴜʟʟᴇᴛ ᴛʀᴀᴄᴋ] 大範圍子彈 °", ---u1
    "° [小丑 + AK47] °", ---v1
    "° [ᴍᴘ] 紅色透視 °", ---red
    "° [ᴍᴘ] 黑色天空 °", ---black 
    "∆•••⛔ [EXIT] ° [離開] ⛔•••∆", ---exit
}, nil, os["date"]("\n📅 Date : %A %d %B %Y\n⏰ Time : %H:%M %p\n°ʜᴀᴄᴋ ʙʏ 🐮Bᴜᴛᴛᴇʀ"))
    if menu == nil then
        else
    if menu[1] == true then a1()
        end
    if menu[2] == true then b1()
        end
    if menu[3] == true then c1()
        end
    if menu[4] == true then d1()
        end
    if menu[5] == true then e1()
        end
    if menu[6] == true then f1()
        end
    if menu[7] == true then g1()
        end
    if menu[8] == true then h1()
        end
    if menu[9] == true then i1()
        end
    if menu[10] == true then j1()
        end
    if menu[11] == true then k1()
        end
    if menu[12] == true then l1()
        end
    if menu[13] == true then m1()
        end
    if menu[14] == true then n1()
        end
    if menu[15] == true then o1()
        end
    if menu[16] == true then p1()
        end
    if menu[17] == true then q1()
        end
    if menu[18] == true then r1()
        end
    if menu[19] == true then s1()
        end
    if menu[20] == true then t1()
        end
    if menu[21] == true then u1()
        end
    if menu[22] == true then v1()
        end
    if menu[23] == true then red()
        end
    if menu[24] == true then black()
        end
    if menu[25] == true then exit()
        end
     end
   COW = -1
end

---- Values ----
function a1()
gg.clearResults()
gg.setRanges(gg.REGION_C_DATA | gg.REGION_CODE_APP)
gg.setVisible(false)
gg.searchNumber("-2067906082;-1731059524;1658658271;1591671054;953729732:16384", gg.TYPE_DWORD, false, gg.SIGN_EQUAL, 0, -1, 0)
revert = gg.getResults(99999, nil, nil, nil, nil, nil, nil, nil, nil)
local t = gg.getResults(99999, nil, nil, nil, nil, nil, nil, nil, nil)
for i, v in ipairs(t) do
  if v.flags == gg.TYPE_DWORD then
    v.value = "0"
    v.freeze = true
  end
end
gg.addListItems(t)
t = nil
gg.clearResults()
gg.clearList()
gg.sleep(300)
gg.setVisible(false)

a = "24008\nVar #B1FAB030|b1fab030|4|6234b402|0|0|0|0|rw-p|data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|30"
fileData = gg.EXT_STORAGE .. "/[#timi#].dat"
io.output(fileData):write(a):close()
gg.loadList(fileData, gg.LOAD_APPEND)
gg.sleep(50)
r = gg.getListItems()
gg.loadResults(r)
revert = gg.getResults(10000, nil, nil, nil, nil, nil, nil, nil, nil)
local t = gg.getResults(10000, nil, nil, nil, nil, nil, nil, nil, nil)
for i, v in ipairs(t) do
  if v.flags == gg.TYPE_DWORD then
    v.value = "0"
    v.freeze = true
  end
end
gg.addListItems(t)
t = nil
gg.clearResults()
gg.clearResults()
gg.setVisible(false)

b = "2324\nVar #BC34A9CC|bc34a9cc|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|9cc\nVar #BC34A9D4|bc34a9d4|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|9d4\nVar #BC34A9DC|bc34a9dc|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|9dc\nVar #BC34A9E8|bc34a9e8|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|9e8\nVar #BC34A9F0|bc34a9f0|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|9f0\nVar #BC34A9F8|bc34a9f8|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|9f8\nVar #BC34AA00|bc34aa00|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a00\nVar #BC34AA08|bc34aa08|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a08\nVar #BC34AA10|bc34aa10|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a10\nVar #BC34AA18|bc34aa18|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a18\nVar #BC34AA20|bc34aa20|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a20\nVar #BC34AA30|bc34aa30|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a30\nVar #BC34AA38|bc34aa38|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a38\nVar #BC34AA58|bc34aa58|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a58\nVar #BC34AA60|bc34aa60|4|4000|0|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|a60"
fileData = gg.EXT_STORAGE .. "/[#tencent#].dat"
io.output(fileData):write(b):close()
gg.loadList(fileData, gg.LOAD_APPEND)
gg.sleep(50)
r = gg.getListItems()
gg.loadResults(r)
revert = GR(10000, nil, nil, nil, nil, nil, nil, nil, nil)
local t = GR(10000, nil, nil, nil, nil, nil, nil, nil, nil)
for i, v in ipairs(t) do
  if v.flags == DWORD then
    v.value = "67,109,633"
    v.freeze = true
  end
end
gg.addListItems(t)
t = nil
gg.clearResults()
gg.clearResults()
gg.setVisible(false)

c = "19170\nVar #BDDDFEE8|bdddfee8|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|20ee8\nVar #BDDDFEEC|bdddfeec|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|20eec\nVar #BDDDFEF0|bdddfef0|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|20ef0\nVar #BDDDFEF4|bdddfef4|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|20ef4\nVar #BDDDFEF8|bdddfef8|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|20ef8\nVar #BDDDFEFC|bdddfefc|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so|20efc\nVar #BDDE0144|bdde0144|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|144\nVar #BDDE015C|bdde015c|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|15c\nVar #BDDE0160|bdde0160|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|160\nVar #BDDE0164|bdde0164|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|164\nVar #BDDE0168|bdde0168|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|168\nVar #BDDE016C|bdde016c|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|16c\nVar #BDDE0170|bdde0170|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|170\nVar #BDDE0174|bdde0174|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|174\nVar #BDDE0178|bdde0178|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|178\nVar #BDDE017C|bdde017c|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|17c\nVar #BDDE0180|bdde0180|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|180\nVar #BDDE0184|bdde0184|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|184\nVar #BDDE0188|bdde0188|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|188\nVar #BDDE01A4|bdde01a4|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|1a4\nVar #BDDE01A8|bdde01a8|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|1a8\nVar #BDDE0248|bdde0248|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|248\nVar #BDDE024C|bdde024c|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|24c\nVar #BDDE0250|bdde0250|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|250\nVar #BDDE0254|bdde0254|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|254\nVar #BDDE0260|bdde0260|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|260\nVar #BDDE0264|bdde0264|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|264\nVar #BDDE02A4|bdde02a4|4|0|1|0|0|0|rw-p|/data/app/com.garena.game.codm-awDI-3XXH8JoohoTgyw17w==/lib/arm/libanogs.so:bss|2a4"
fileData = gg.EXT_STORAGE .. "/[###].dat"
io.output(fileData):write(c):close()
gg.loadList(fileData, gg.LOAD_APPEND)
gg.sleep(50)
r = gg.getListItems()
gg.loadResults(r)
revert = gg.getResults(10000, nil, nil, nil, nil, nil, nil, nil, nil)
local t = gg.getResults(10000, nil, nil, nil, nil, nil, nil, nil, nil)
for i, v in ipairs(t) do
  if v.flags == gg.TYPE_DWORD then
    v.value = "0"
    v.freeze = true
  end
end
gg.addListItems(t)
t = nil
gg.clearResults()
gg.toast("⭕ ʟᴏɢᴏ ʙʏᴘᴀss ᴀᴄᴛɪᴠᴇ✔")
end

 ---- Values ----
function b1()
RANGE(CA)
SET(false)
SN("131,330;134,402", DWORD)
REFINE("131,330", DWORD)
GR(50500)
EA("16,777,985", DWORD)
gg.clearResults()
RANGE(CA)
SET(false)
SN("196,867;67,109,633", DWORD)
REFINE("196,867", DWORD)
GR(50500)
EA("16,777,985", DWORD)
gg.clearResults()
RANGE(CA)
SET(false)
SN("144,387;132,098", DWORD)
REFINE("144,387", DWORD)
GR(50500)
EA("67,109,092", DWORD)
gg.clearResults()
RANGE(CA)
SET(false)
SN("134,402;134,658", DWORD)
REFINE("134,402", DWORD)
GR(50500)
EA("133,890", DWORD)
gg.clearResults()
RANGE(CA)
SET(false)
SN("134,914;262,403", DWORD)
REFINE("134,914", DWORD)
GR(50500)
EA("133,890", DWORD)
gg.clearResults()
RANGE(CA)
SET(false)
SN("262,403;134,658", DWORD)
REFINE("262,403", DWORD)
GR(50500)
EA("133,890", DWORD)
gg.clearResults()
gg.toast("🔐 ʙʏᴘᴀss ʟᴏʙʙʏ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function c1()
SET(false)
RANGE(AN) 
local S = {{1082130432, 0}, {1065353216, 4}, {1065353216, 8}, {0, 16}, {1077936128, 20},}
local W = {{1073741824, 0}, {1086324736, 4}, {1203982336, 8}, {0, 16}, {1077936128, 20},}
local T = DWORD
AxM(S, W, T)
gg.clearResults()
RANGE(AN) 
local S = {{1077936128, 0}, {1028443341, 4}, {1061997773, 8}, {1065353216, 16}, {1065353216, 20},}
local W = {{1077936128, 0}, {1028443341, 4}, {-1007026176, 8}, {1065353216, 16}, {1065353216, 20},}
local T = DWORD
AxM(S, W, T)
gg.clearResults()
RANGE(AN) 
local S = {{1077936128, 0}, {0, 4}, {1053609165, 8}, {1065353216, 16}, {1065353216, 20},}
local W = {{1077936128, 0}, {0, 4}, {-1007026176, 8}, {1065353216, 16}, {1065353216, 20},}
local T = DWORD
AxM(S, W, T)
gg.clearResults()
gg.toast("🔵 (ʙʟᴜᴇ) ᴀɴᴛʜᴇɴᴀ ғʀᴀᴍᴇ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function d1()
SET(false)
HexPatches.MemoryPatch('libil2cpp.so', 0x1B53EA4, '0170A0E3', 4)
HexPatches.MemoryPatch('libil2cpp.so', 0x1131978, '000051E3', 4)
HexPatches.MemoryPatch('libil2cpp.so', 0x2028ACC, '000050E3', 4)
HexPatches.MemoryPatch('libil2cpp.so', 0x11320A0, '000050E3', 4)
gg.clearResults()
gg.toast("☮️ ᴇsᴘ ɴᴀᴍᴇ [ʙʀ] ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function e1()
RANGE(AN)
SN("0.1439999938", DWORD)
GR(99999, nil, nil, nil, nil, nil, nil, nil, nil)
EA("1.1439999938", DWORD)
gg.clearResults()
gg.toast("🎯 ᴍᴀɢɪᴄ ʙᴜʟʟᴇᴛ ʙʀ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function f1()
RANGE(AN)
SET(false)
SN("4.28000020981;3.20000004768;0.30000001192;0.20000000298", FLOAT, false, gg.SIGN_EQUAL, 0, -1)
revert = GR(50000, nil, nil, nil, nil, nil, nil, nil, nil)
local t = GR(50000, nil, nil, nil, nil, nil, nil, nil, nil)
for i, v in ipairs(t) do
if v.flags == FLOAT then
    v.value = "15"
    v.freeze = true
  end
end
gg.addListItems(t)
t = nil
gg.clearResults()
gg.clearList()
gg.toast("💨 [ʙʀ] °ғᴀsᴛᴇʀ° ʀᴜɴ x15 ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function g1()
RANGE(AN)
SET(false)
SN("4.28000020981;3.20000004768;0.30000001192;0.20000000298", FLOAT, false, gg.SIGN_EQUAL, 0, -1)
revert = GR(10000, nil, nil, nil, nil, nil, nil, nil, nil)
local t = GR(10000, nil, nil, nil, nil, nil, nil, nil, nil)
for i, v in ipairs(t) do
if v.flags == FLOAT then
    v.value = "9.54546798999"
    v.freeze = true
  end
end
gg.addListItems(t)
t = nil
gg.clearResults()
gg.clearList()
gg.toast("🏃🏻‍♂️ ғʟᴀsʜ ʀᴜɴ x5 ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function h1()
RANGE(AN)
SET(false)
SN("4.28000020981", FLOAT, false, gg.SIGN_EQUAL, 0, -1)
GR(1000)
EA("5.14546798999", FLOAT)
gg.clearResults()
gg.toast("🐢 sᴘᴇᴇᴅ ʀᴜɴ x3 ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function i1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x1A74904
setvalue(so + py, 4, 0)
gg.clearResults()
gg.toast("👀 ᴡᴀʟʟнᴀᴄᴋ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function j1()
SET(false)
HexPatches.MemoryPatch('libil2cpp.so', 0x6661A48, '220244E3', 4)
gg.clearResults()
gg.toast("🔫 ᴀɪᴍʙᴏᴛ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function k1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x1bce4d4
setvalue(so + py, 16, 0.5)
gg.clearResults()
gg.toast("🀄 ᴀɪᴍʟᴏᴄᴋ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function l1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x1ba96a8      
setvalue(so + py, 10, '0x0')
gg.clearResults()
gg.toast("👁️ ғᴀsᴛ sᴄᴏᴘᴇ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function m1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x4ebd034
setvalue(so + py, 10, '0x0')
gg.clearResults()
gg.toast("📍ѕмall croѕѕнaιr ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
---HexPatches.MemoryPatch('libil2cpp.so', 0x33EA0B4, '9900A0E31EFF2FE1', 32)
function n1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x36b9b00      
setvalue(so + py, 16, 0)
gg.clearResults()
gg.toast("🕳️ ɴᴏ ʀᴇᴄᴏɪʟ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function o1()
SET(false)
HexPatches.MemoryPatch('libil2cpp.so', 0x1C0C48C, '0', 4)
HexPatches.MemoryPatch('libil2cpp.so', 0x262671C, '0', 4)
gg.clearResults()
gg.toast("🤹 ғᴀsᴛ ʀᴇʟᴏᴀᴅ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function p1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x33e901c      
setvalue(so + py, 16, 1)
gg.clearResults()
so = RL('libil2cpp.so')[1].start
local py = 0x33fd654      
setvalue(so + py, 16, 1)
gg.clearResults()
gg.toast("ɴᴏ sᴘʀᴇᴀᴅ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function q1()
SET(false)
HexPatches.MemoryPatch('libil2cpp.so', 0x5EE8B8C, '0100A0E31EFF2FE1', 32)
gg.clearResults()
gg.toast("ʀᴀᴅᴀʀ ʜᴀᴄᴋ ᴀᴄᴛɪᴠᴇ✔")
end

---- No Parachute  ----
function r1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x20B49F8
setvalue(so + py, 16, '-5.90295867e21')
gg.clearResults()
so = RL('libil2cpp.so')[1].start
local py = 0x20B49FC
setvalue(so + py, 16, '-2.02910209e20')
gg.clearResults()
gg.toast("No Parachute ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function s1()
SET(false)
so = RL('libil2cpp.so')[1].start
local py = 0x262456c
setvalue(so + py, 16, 0)

so = RL('libil2cpp.so')[1].start
local py = 0x2626168
setvalue(so + py, 16, 0)
gg.clearResults()
gg.toast("🌡️ ғᴀsᴛsʜσσᴛ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function t1()
RANGE(AN)
SET(false)
SN("0.1439999938", FLOAT, false, gg.SIGN_EQUAL, 0, -1, 0)
GR(1000)
EA("1.9", FLOAT)
gg.clearResults()
gg.toast("🎯 ᴍᴀɢɪᴄ ʙᴜʟʟᴇᴛ 80% ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function u1()
SET(false)
so = RL('libunity.so')[1].start
local py = 0xB68E04
setvalue(so + py, 16, 23)
gg.clearResults()
so = RL('libunity.so')[1].start
local py = 0xB68E08
setvalue(so + py, 16, 23)
gg.clearResults()
so = RL('libunity.so')[1].start
local py = 0xB68F10
setvalue(so + py, 16, 23)
gg.clearResults()
so = RL('libunity.so')[1].start
local py = 0x515338
setvalue(so + py, 16, 9.5)
gg.clearResults()
so = RL('libunity.so')[1].start
local py = 0xB68E0C
setvalue(so + py, 16, 0)
gg.clearResults()
gg.toast("🚫 ʙᴜʟʟᴇᴛ ᴛʀᴀᴄᴋ ᴀᴄᴛɪᴠᴇ✔")
end

---- Values ----
function v1()
RANGE(AN)
SET(false)
SN("100,000,088;0;100,000,086;100,000,078;100,000,088;100,000,083;100,000,078;100,000,088::45", DWORD)
GR(10000)
EA("710,001,783;289,900,005;100,000,086;710,001,785;710,001,783;710,001,784;710,001,785;710,001,783", DWORD)
gg.clearResults()
gg.toast("狂暴小丑 ᴀᴄᴛɪᴠᴇ✔")
SET(false)
gg.clearResults()
gg.sleep(200)

RANGE(AN)
SET(false)
SN("2;30;200000029;200000233;200002161::21", DWORD)
GR(10000)
EA("100524;100233;66734;66740;66737", DWORD)
gg.clearResults()
RANGE(AN)
SET(false)
SN("200,002,161;10107001;1,057,803,469::31", DWORD)
REFINE("200002161", DWORD)
GR(10000)
EA("66737", DWORD)
gg.clearResults()
gg.toast("ᴀᴋ47 ʀᴀᴅɪᴀɴᴄᴇ ᴀᴄᴛɪᴠᴇ✔")
end

---- red ----
function red()
SET(false)
so = RL('libunity.so')[1].start
local py = 0x3e3df8     
setvalue(so + py, 4, 80)
gg.clearResults()
gg.toast("紅色透視 [ᴍᴘ] ᴀᴄᴛɪᴠᴇ✔")
end

---- black ----
function black()
SET(false)
so = RL('libunity.so')[1].start
local py = 0x15d814
setvalue(so + py, 16, 10)
gg.clearResults()
gg.toast("黑色天空 [ᴍᴘ] ᴀᴄᴛɪᴠᴇ✔")
end


---- Exit ----
    function exit()
        gg["alert"](" See You ")
        gg["toast"]("🐮 Script End 🐮")
        gg["skipRestoreState"]()
        gg["setVisible"](true)
        os["exit"]()
      end

while true do
    if gg["isVisible"](true) then COW = 1
        gg["setVisible"](false) end
            if COW == 1 then Main()
        gg["clearResults"]()
    end
end
---- End ----








