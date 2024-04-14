# sqlsave
เกี่ยวกับการเซฟข้อมูลแบบทันทีโดยช่วย save ความหน่วงได้ในระยะหนึ่ง

    Player_SetSkin(playerid, skinid, bool:save = false) {
      playerData[playerid][pSkin] = skinid;

      if (save) {
          new query[95];
  
          mysql_format(g_SQL, query, sizeof(query), "\
              UPDATE \
                  players \
              SET \
                  skin = %d \
              WHERE \
                  u_id = %d\
          ",
              skinid,
              playerData[playerid][pID]
          );
      }
    }
