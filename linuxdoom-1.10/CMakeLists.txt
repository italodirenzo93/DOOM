cmake_minimum_required(VERSION 3.16)
project(linuxdoom_1_10 C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake-modules/")

add_compile_definitions(SDL NORMALUNIX SNDSERV SNDSRV)

find_package(SDL2 REQUIRED COMPONENTS main)
if(NOT WIN32)
    find_package(OpenGL REQUIRED)
endif()

include_directories(${SDL2_INCLUDE_DIRS} ${SDL2main_INCLUDE_DIRS} ${OPENGL_INCLUDE_DIR} ${CMAKE_BINARY_DIR})

add_executable(linuxdoom_1_10
        am_map.c
        d_items.c
        d_main.c
        d_net.c
        doomdef.c
        doomstat.c
        dstrings.c
        f_finale.c
        f_wipe.c
        g_game.c
        hu_lib.c
        hu_stuff.c
        i_main.c
        i_net.c
        i_sound.c
        i_system.c
        i_video.c
        info.c
        m_argv.c
        m_bbox.c
        m_cheat.c
        m_fixed.c
        m_menu.c
        m_misc.c
        m_random.c
        m_swap.c
        p_ceilng.c
        p_doors.c
        p_enemy.c
        p_floor.c
        p_inter.c
        p_lights.c
        p_map.c
        p_maputl.c
        p_mobj.c
        p_plats.c
        p_pspr.c
        p_saveg.c
        p_setup.c
        p_sight.c
        p_spec.c
        p_switch.c
        p_telept.c
        p_tick.c
        p_user.c
        r_bsp.c
        r_data.c
        r_draw.c
        r_main.c
        r_plane.c
        r_segs.c
        r_sky.c
        r_things.c
        s_sound.c
        sounds.c
        st_lib.c
        st_stuff.c
        tables.c
        v_video.c
        w_wad.c
        wi_stuff.c
        z_zone.c)

target_link_libraries(linuxdoom_1_10 ${SDL2_LIBRARIES})
