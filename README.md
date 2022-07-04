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
    "∆•••⛔ [EXIT] ° [離開] ⛔•••∆", ---exit
}, nil, os["date"]("\n📅 Date : %A %d %B %Y\n⏰ Time : %H:%M %p\n°ʜᴀᴄᴋ ʙʏ 🐮Bᴜᴛᴛᴇʀ"))
    if menu == nil then 
      else
    if menu[1] == true then a1()
      end
    if menu[2] == true then exit()
    end
  COW = -1
end
    
---- a1 ----
function a1()
  gg.print("Sorry, its the time to expired\n\n if you want to buy my script\n\nPlease contact me:\nWhataApp:+852 51774264")
  gg.clearResults()
end


---- Exit ----
function exit()
  ex = gg["alert"]("EXIT？ • 離開？", "⭕ Yes ⭕", "🔙 Back 🔙", nil)
    if ex == nil then else
    if ex == 1 then
      gg["toast"]("😘 Thank You For Use 😘\n\n  💘 Love You All 💘")
      gg["skipRestoreState"]()
      gg["setVisible"](true)
      os["exit"]()
      end
    if ex == 2 then
      end
      end
      end

---- End ----
  while true do
    if gg["isVisible"](true) then COW = 1
      gg["setVisible"](false) end
      gg["clearResults"]()
    if COW == 1 then Main()
      end
      end








