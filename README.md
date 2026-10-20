# Avalanche Lua API

Flat, exhaustive reference of the **entire** Avalanche Lua scripting API.

> **Auto-generated — do not edit.** Derived from the in-game registry (`Avalanche LuaApiRegistry`, schema v1) via `npm run gen-lua-api`. For the full interactive docs (with prose walkthroughs, worked example scripts, and search) see **https://avalan.cc/developers/lua**.

**105** scopes · **1648** members · **16** globals · **40** callbacks · **3** constants

**Trust tiers:** `safe` (available to every script, default) · `privileged` (low-level / powerful — TRUSTED scripts only) · `internal` (engine-only).

## Contents

- [Scopes](#scopes)
  - [Vector3](#vector3)
  - [Vec2](#vec2)
  - [Angle](#angle)
  - [Color](#color)
  - [Ability](#ability)
  - [PlayerPawn](#playerpawn)
  - [Entity](#entity)
  - [PlayerController](#playercontroller)
  - [Modifier](#modifier)
  - [UserCmd](#usercmd)
  - [CUserCmd](#cusercmd)
  - [CallbackHandle](#callbackhandle)
  - [AddedCallbackHandle](#addedcallbackhandle)
  - [MenuNode](#menunode)
  - [MenuPanel](#menupanel)
  - [File](#file)
  - [GameEvent](#gameevent)
  - [raw_struct](#raw_struct)
  - [trace](#trace)
  - [mem](#mem)
  - [hooks](#hooks)
  - [HookHandle](#hookhandle)
  - [Schema](#schema)
  - [prediction](#prediction)
  - [nav](#nav)
  - [safety](#safety)
  - [action](#action)
  - [trigger](#trigger)
  - [Backtrack](#backtrack)
  - [log](#log)
  - [lua_convar_t](#lua_convar_t)
  - [lua_target_selection_wrapper_t](#lua_target_selection_wrapper_t)
  - [Particle](#particle)
  - [particle](#particle)
  - [ParticleHandle](#particlehandle)
  - [http](#http)
  - [HttpRequest](#httprequest)
  - [net_channel](#net_channel)
  - [net](#net)
  - [proto](#proto)
  - [common](#common)
  - [anim](#anim)
  - [color](#color)
  - [config_state](#config_state)
  - [esp](#esp)
  - [esp.enemy](#espenemy)
  - [EspElement](#espelement)
  - [EspClass](#espclass)
  - [MenuInject](#menuinject)
  - [HeroCfg](#herocfg)
  - [ComboOpt](#comboopt)
  - [ComboOptScope](#combooptscope)
  - [feature](#feature)
  - [Panorama](#panorama)
  - [PanoramaPanel](#panoramapanel)
  - [native](#native)
  - [ffi](#ffi)
  - [FFILib](#ffilib)
  - [FFICallable](#fficallable)
  - [FFIScalar](#ffiscalar)
  - [HERO_LIB](#hero_lib)
  - [ANIM_LIB](#anim_lib)
  - [Render](#render)
  - [Menu](#menu)
  - [Aim](#aim)
  - [callback](#callback)
  - [ImGui](#imgui)
  - [Input](#input)
  - [Keys](#keys)
  - [GlowMode](#glowmode)
  - [FrameStage](#framestage)
  - [entity_list](#entity_list)
  - [db](#db)
  - [storage](#storage)
  - [convar](#convar)
  - [global_ctx](#global_ctx)
  - [JSON](#json)
  - [Math](#math)
  - [Game](#game)
  - [Combat](#combat)
  - [player_stats](#player_stats)
  - [AimConfig](#aimconfig)
  - [Notification](#notification)
  - [Vertex](#vertex)
  - [utils](#utils)
  - [draw](#draw)
  - [global_vars](#global_vars)
  - [game_rules](#game_rules)
  - [io](#io)
  - [QAngle](#qangle)
  - [InputBitMask_t](#inputbitmask_t)
  - [Enum.ButtonCode](#enumbuttoncode)
  - [Enum.GroupSide](#enumgroupside)
  - [Enum.ImageFilter](#enumimagefilter)
  - [EAbilitySlots_t](#eabilityslots_t)
  - [ModifierValue](#modifiervalue)
  - [EModifierValue](#emodifiervalue)
  - [WeaponBulletData](#weaponbulletdata)
  - [AimResult](#aimresult)
  - [PlayerTarget](#playertarget)
  - [SoulTarget](#soultarget)
  - [DeployableTarget](#deployabletarget)
  - [AimInput](#aiminput)
  - [AimFailReason](#aimfailreason)
  - [lua_raw_ptr_t](#lua_raw_ptr_t)
- [Global functions](#global-functions)
- [Callbacks](#callbacks)
- [Global constants](#global-constants)

## Scopes

### Vector3

`usertype` · tier `safe` — 3D vector (game world units).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `x` | `.x: number` | safe |  |
| `y` | `.y: number` | safe |  |
| `z` | `.z: number` | safe |  |
| `IsZero` | `:IsZero() -> boolean` | safe |  |
| `Length` | `:Length() -> number` | safe |  |
| `length` | `:length() -> number` | safe |  |
| `length_2d` | `:length_2d() -> number` | safe |  |
| `length_sqr` | `:length_sqr() -> number` | safe |  |
| `dist` | `:dist(other: Vector3) -> number` | safe | Distance in game UNITS (same function as Distance). |
| `dist_2d` | `:dist_2d(other: Vector3) -> number` | safe | Horizontal (x, y) distance in game UNITS (same function as Distance2D). |
| `dot` | `:dot(other: Vector3) -> number` | safe |  |
| `cross` | `:cross(other: Vector3) -> Vector3` | safe |  |
| `normalized` | `:normalized() -> Vector3` | safe |  |
| `lerp` | `:lerp(other: Vector3, t: number) -> Vector3` | safe |  |
| `dir_to` | `:dir_to(other: Vector3) -> Vector3` | safe |  |
| `to_angles` | `:to_angles() -> table` | safe | Direction vector -> { pitch, yaw, roll }. |
| `Distance` | `:Distance(other: Vector3) -> number` | safe | Distance in game UNITS (Math.Distance returns meters). |
| `Distance2D` | `:Distance2D(other: Vector3) -> number` | safe | Horizontal (x, y) distance in game UNITS. |

### Vec2

`usertype` · tier `safe` — 2D vector.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `x` | `.x: number` | safe |  |
| `y` | `.y: number` | safe |  |
| `Length` | `:Length() -> number` | safe | Vector magnitude. |
| `Distance` | `:Distance(other: Vec2) -> number` | safe | Distance to another Vec2. |
| `Normalized` | `:Normalized() -> Vec2` | safe | Unit-length copy (origin if zero-length). |

### Angle

`usertype` · tier `safe` — Euler angle (pitch, yaw, roll in degrees).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `pitch` | `.pitch: number` | safe |  |
| `yaw` | `.yaw: number` | safe |  |
| `roll` | `.roll: number` | safe |  |
| `Forward` | `:Forward() -> Vector3` | safe | Unit forward vector for this angle. |
| `Right` | `:Right() -> Vector3` | safe | Unit right vector for this angle. |
| `Up` | `:Up() -> Vector3` | safe | Unit up vector for this angle. |

### Color

`usertype` · tier `safe` — RGBA color. Construct via Color(r,g,b,a) or ImColor(...).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `r` | `.r: number` | safe |  |
| `g` | `.g: number` | safe |  |
| `b` | `.b: number` | safe |  |
| `a` | `.a: number` | safe |  |
| `with_alpha` | `:with_alpha(a: integer) -> Color` | safe | Copy with alpha replaced. |
| `scale_alpha` | `:scale_alpha(scale: number) -> Color` | safe | Copy with alpha multiplied by scale. |
| `lerp` | `:lerp(other: Color, t: number) -> Color` | safe | Component-wise lerp toward other (t clamped 0..1). |
| `to_hex` | `:to_hex() -> string` | safe | "#RRGGBBAA" hex string. |
| `luminance` | `:luminance() -> number` | safe | Perceptual luminance (0.299r + 0.587g + 0.114b). |

### Ability

`usertype` · tier `safe` — Citadel ability handle (upgrade-aware, identity-revalidated). `a == b` is true for two handles of the same game instance.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe |  |
| `get_name` | `:get_name() -> string` | safe |  |
| `get_class_name` | `:get_class_name() -> string` | safe |  |
| `get_scaled_property` | `:get_scaled_property(key: string) -> number` | safe | Caster-scaled property value: spirit power, item bonuses and upgrades applied. Game thread only; an off-thread call returns the authored base value for that call. Range and length keys come back in UNITS. |
| `list_properties` | `:list_properties() -> table` | safe | Enumerate every authored VData property as { PropertyName = scaledValue } (force-populated, upgrade-aware). Use it to discover a property's EXACT field name. |
| `get_property` | `:get_property(name: string) -> number` | safe | Named property. "cast_range" and "aoe_radius" return the same values as get_cast_range() / get_aoe_radius(); "cooldown" is m_flCooldownEnd - m_flCooldownStart. |
| `get_cast_range` | `:get_cast_range() -> number` | safe | Scaled cast range in UNITS, including cast-range items (Greater Expansion etc.). 4000 when the ability declares no range. Same producer as HERO_LIB.get_cast_range / get_ability_range. |
| `get_aoe_radius` | `:get_aoe_radius() -> number` | safe | Scaled AoE radius in UNITS (metre values converted); 0 when the ability declares none. Same producer as HERO_LIB.get_aoe_radius. For the circle the engine itself draws, use game_aoe_radius(). |
| `targeting_shape` | `:targeting_shape() -> integer` | safe | The GAME'S cast SHAPE (EAbilityTargetingShape_t) via the engine's own getter: 2=line/trajectory, 3=AoE circle, 4=cone, 5=radius. 0 = none/invalid. Use it to know how an ability actually targets (e.g. shape==4 => cone). |
| `targeting_cone_angle` | `:targeting_cone_angle() -> number` | safe | The ability's cone spread in DEGREES, UPGRADE-AWARE (the game's own getter, not the base VData field — so it reflects scaling items). FULL angle: a target is inside the cone when its angular deviation from the aim axis is <= angle/2. 0 if no cone. |
| `targeting_cone_half_width` | `:targeting_cone_half_width() -> number` | safe | The cone's near-field half-width the preview draws alongside the angular spread (game's own getter, upgrade-aware). 0 if unauthored. |
| `game_aoe_radius` | `:game_aoe_radius() -> number` | safe | The AoE-circle radius the ENGINE draws (units), from the ability's OWN virtual — UPGRADE-AWARE (folds in Greater Expansion etc.), vs get_aoe_radius's property-key probe. 0 for a non-AoE ability. (Build-specific vtable slot; re-verified via snowpack on patches.) |
| `activation_order` | `:activation_order() -> integer` | safe | The GAME'S OWN ECitadelAbilityOrders cast-validity for THIS ability right now — the exact code that greys/blacks its HUD icon. 0 = Success (castable). 10 = BusyWithAction: blocked because the hero is mid ability animation (the state where all other abilities black out). Other codes = cooldown/charge/silence/etc. GetAbilityActivationOrder (vtable slot 270 as of 2026-09-30; was 266), a pure query. Truthful when the aggregate BUSY_WITH_ACTION modifier lags a busy animation. -1 on a dead ability. (Build-specific slot; re-verify via snowpack on patches.) |
| `get_slot` | `:get_slot() -> integer` | safe | The game's slot for this ability (m_eAbilitySlot, EAbilitySlots_t): signatures 0..3, active items 4..7, primary weapon 21. -1 if not live. |
| `get_level` | `:get_level() -> integer` | safe |  |
| `get_target` | `:get_target() -> PlayerPawn\|nil` | safe |  |
| `get_upgrades` | `:get_upgrades() -> table\|nil` | safe |  |
| `get_upgrade` | `:get_upgrade(level: integer) -> boolean` | safe |  |
| `find_entities_in_cone` | `:find_entities_in_cone(range: number, angle_deg: number) -> PlayerPawn[]` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_imbued_abilities` | `:get_imbued_abilities() -> table` | safe | Abilities this item has imbued (items with an imbue target only, e.g. Echo Shard, Mystic Reverb). Matched by the ability's subclass identity (m_nSubclassID). |
| `has_imbue_for` | `:has_imbue_for(...: any) -> boolean` | safe | True if this item has imbued the given ability. Accepts an Ability, a subclass token, or an ability class name. |
| `get_raw_vdata` | `:get_raw_vdata() -> raw_struct\|nil` | privileged |  |
| `get_raw_struct` | `:get_raw_struct() -> raw_struct\|nil` | privileged |  |
| `get_vdata` | `:get_vdata() -> table\|nil` | safe | A read-only schema view of the ability's vdata: fields by schema name, embedded classes as nested views (vdata.m_projectileInfo.m_flSpeed, vdata.m_eAbilityActivation). No address and no writers, so it is not gated like raw_struct. A view kept past a map change reads whatever lives there now; ask again rather than keep one. nil without vdata. |
| `is_on_cooldown` | `:is_on_cooldown() -> boolean` | safe |  |
| `cooldown` | `:cooldown() -> number` | safe |  |
| `charges` | `:charges() -> integer` | safe |  |
| `can_be_executed` | `:can_be_executed() -> integer` | safe |  |
| `can_activate` | `:can_activate() -> boolean` | safe | Authoritative "can I press this ability/item button right now?" (cooldown/charges/cast-delay + stun/silence/mute gates). Also false on a zipline unless the ability may be cast there, and false while climbing a rope unless the ability cancels the climb. |
| `true_cooldown` | `:true_cooldown() -> number` | safe | Seconds until genuinely usable again: 0 = now, >0 = time to the NEXT USABLE CHARGE (per-charge recharge, not the full cooldown). |
| `is_cooling_down` | `:is_cooling_down() -> boolean` | safe | True while cooldown or charge-recharge time remains. CHANGED: used to be true forever after the first cast. |
| `get_cooldown_start` | `:get_cooldown_start() -> number` | safe | Game time the current cooldown started (m_flCooldownStart). CHANGED: used to return the cast-delay start time. |
| `get_cooldown_end` | `:get_cooldown_end() -> number` | safe | Game time the current cooldown ends (m_flCooldownEnd). |
| `get_cooldown_duration` | `:get_cooldown_duration() -> number` | safe | Length of the current cooldown in seconds (m_flCooldownEnd - m_flCooldownStart). |
| `is_refresh_item` | `:is_refresh_item() -> boolean` | safe | True iff this is a cooldown-reset ITEM: Echo Shard (PowerShard) or Refresher. Matched on the stable class-binding + designer token. |
| `has_refresh_target` | `:has_refresh_target() -> boolean` | safe | For a cooldown-reset item, whether the game would currently ACCEPT the cast (something IS refreshable) — i.e. NOT the "nothing to refresh" rejection that can_activate folds in. Refresher scans the whole signature kit; Echo Shard scans ONLY its own imbued abilities. False for a non-refresh item. |
| `can_place_on` | `:can_place_on(entity: PlayerPawn) -> boolean` | safe | Targeting validity: can this ability/item be placed on THIS candidate entity right now? Per-target companion of can_activate (which is target-independent). Replicates the game's per-candidate cast-validity from the ability's own vdata — location + team/type (ally/enemy/self) + range + cone + LOS — uniform for any ability/item on any hero. READ-ONLY query. |
| `has_alt_cast` | `:has_alt_cast() -> boolean` | safe | Does the ability support a SELF/ALT cast? True when its VData authors an alt-cast button token (the game's own marker for a self/no-target variant). Introspection for the engine's self-cast forcing: a step with TargetMode=Self presses IN_ALT_CAST so the cast lands on the local player regardless of the player's Quick/Confirm/Self cast setting. |
| `targeting_location` | `:targeting_location() -> integer` | safe | Raw targeting location (CITADEL_ABILITY_TARGETING_LOCATION / m_eAbilityTargetingLocation): 0 NONE (skillshot) · 1 SELF · 2 UNIT · 3 GROUND · 4 UNIT_OR_GROUND · 5 FIXED_RANGE_GROUND · 6 MINIMAP_GROUND · 7 MINIMAP_UNIT · 8 CUSTOM · 9 DEPLOYED_OBJECT. -1 if dead/unreachable. Static targeting metadata read off the live VData. The combo engine routes casts on this — can_place_on is meaningful ONLY for the UNIT kinds. |
| `is_unit_targeted` | `:is_unit_targeted() -> boolean` | safe | Is this an auto-aim, UNIT-targeted ability — targeting_location in {UNIT, UNIT_OR_GROUND, MINIMAP_UNIT}? True iff ability:can_place_on is the authoritative per-target validity gate for it. False for a skillshot (NONE), a ground/point cast, a self cast, or an unreachable VData — exactly the cases where can_place_on is meaningless and must NOT gate the cast. |
| `target_types` | `:target_types() -> integer` | safe | Raw CITADEL_UNIT_TARGET_TYPE bitfield (m_nAbilityTargetTypes) — which unit relationships the ability/item MAY target. Key bits: HERO_FRIENDLY 0x1 (allies, INCLUDES the caster/self), HERO_ENEMY 0x100. 0 if dead/unreachable. Static metadata off the live VData (the field SelfCastCatalog reads). With targeting_location/is_unit_targeted it classifies self-cast vs skillshot (loc==NONE: no enemy bit => self, enemy bit => skillshot) and the ally-vs-enemy side of a unit-attach item. |
| `__index` | `:__index(key: string) -> any` | privileged | Dynamic fallback after named methods: an m_*-prefixed key reads the live schema field off the ability's runtime class (m_flCastDelayStartTime/m_bChanneling/m_bHitAPlayer special-cased). Unknown -> nil (e.g. ability.m_flCooldownEnd). m_ reads resolve against the whole binding chain, so fields of intermediate classes (the melee base's m_eCurrentAttackState, ...) read too. |
| `get_handle` | `:get_handle() -> integer\|nil` | safe | The packed entity handle, the number entity:get_handle() returns; nil when the ability is not live. |
| `get_weapon_info` | `:get_weapon_info() -> table\|nil` | safe | The authored bullet data of the ability's weapon info (the "primary" entry of its vdata's m_mapWeaponInfos) as a fresh table; each key is present only when this build's schema declares its field: bullet_speed (units/s), bullet_gravity (m_flBulletGravityScale x sv_gravity), bullet_gravity_scale, bullet_lifetime (s), radius (vs entities), radius_vs_world, cycle_time (s), damage, range, vertical_aim_bias. nil without weapon info. |
| `get_alt_cast_hold_start_time` | `:get_alt_cast_hold_start_time() -> number` | safe | Game time the alt-cast (self-cast) hold began; 0 while none is in progress. |
| `get_alt_cast_doubletap_start_time` | `:get_alt_cast_doubletap_start_time() -> number` | safe | Game time the alt-cast double tap began; 0 while none is in progress. |
| `get_stolen_slot` | `:get_stolen_slot() -> integer\|nil` | safe | For an ability Sinclair has actively stolen: the slot it was stolen from (m_eStolenInSlot.m_eStolenSlot, 0-based like get_slot). nil when it is not actively stolen. |

### PlayerPawn

`usertype` · tier `safe` — Citadel player pawn (hero entity). Its scalar reads (team, health, alive, flags, velocity, dormancy, eye and view, relation, modifier states, hero / steam id / name) come from the per-tick entity frame and can lag the live pawn by up to one tick; in render callbacks get_origin / get_abs_origin / distance_to* are this frame's drawn position once the pawn is drawn. `a == b` is true for two handles of the same game instance.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe |  |
| `is_alive` | `:is_alive() -> boolean` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_origin` | `:get_origin() -> Vector3` | safe | On the game thread, the per-tick origin: the same value for the whole tick, and the same value HERO_LIB.get_origin returns; use it there for tick-consistent math. Off the game thread (render callbacks), the live interpolated origin of the same pawn, so a world-to-screen does not lag a tick. (0,0,0) for a stale pawn. |
| `get_velocity` | `:get_velocity() -> Vector3` | safe | Networked velocity (units/s) from the tick snapshot (can lag one tick). |
| `get_name` | `:get_name() -> string` | safe |  |
| `get_handle` | `:get_handle() -> integer\|nil` | safe | Full raw CHandle value (entry index + SERIAL bits); nil when the pawn is not live. Identical in meaning to Entity:get_handle(). Use this as a cache key when you need ENTITY IDENTITY: because it carries the serial, a recycled entry slot produces a DIFFERENT key (a cache miss) instead of silently hitting the dead occupant's entry. CHANGED: this previously returned the bare entry index (no serial) and 0 when not live -- so `if not h` never fired (0 is truthy in Lua) and recycled slots caused wrong cache hits. If you want the bare slot, use get_index(). |
| `get_index` | `:get_index() -> integer` | safe | Entity ENTRY index (bare slot, NO serial bits). The right key for a cache that means "this slot" and does not need entity identity; for an identity-stable key use get_handle(). Unchanged. |
| `get_vdata_class_name` | `:get_vdata_class_name() -> string` | safe |  |
| `get_health` | `:get_health() -> number` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_max_health` | `:get_max_health() -> number` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_scaling_stat` | `:get_scaling_stat(stat_type: integer) -> number` | safe |  |
| `get_starting_stat` | `:get_starting_stat(stat_type: integer) -> number` | safe |  |
| `get_modifier_value` | `:get_modifier_value(mod_type: integer, default_value?: number) -> number` | safe | mod_type is an EModifierValue number (the EModifierValue / ModifierValue tables; never a literal). Tech power, max health and bullet / tech resist answer the live stat; every other value is the sum of the pawn's enabled modifiers' scripted values plus their abilities' tagged properties. default_value (0) when nothing provides the value or off the game thread. CHANGED: it used to answer only the four stat-backed values and the ModifierValue numbers were made up (see ModifierValue). |
| `get_sum_modifier_value` | `:get_sum_modifier_value(mod_type: integer, default_value?: number) -> number` | safe | Same answer as get_modifier_value. mod_type is an EModifierValue number (the EModifierValue / ModifierValue tables; never a literal). Tech power, max health and bullet / tech resist answer the live stat; every other value is the sum of the pawn's enabled modifiers' scripted values plus their abilities' tagged properties. default_value (0) when nothing provides the value or off the game thread. CHANGED: it used to answer only the four stat-backed values and the ModifierValue numbers were made up (see ModifierValue). |
| `can_be_lasthitted` | `:can_be_lasthitted(...: any) -> boolean` | safe |  |
| `get_team` | `:get_team() -> integer` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_class_name` | `:get_class_name() -> string` | safe |  |
| `get_tech_resist` | `:get_tech_resist() -> number` | safe | Spirit (tech) resist in PERCENT (30 = 30%). Game thread only (0 elsewhere). For a fraction use get_tech_resist_frac(). |
| `get_bullet_resist` | `:get_bullet_resist() -> number` | safe | Bullet resist in PERCENT (30 = 30%). Game thread only (0 elsewhere). For a fraction use get_bullet_resist_frac(). |
| `get_tech_resist_frac` | `:get_tech_resist_frac() -> number` | safe | Spirit (tech) resist as a fraction (0.30 = 30%). Not clamped: negative under resist shred. Game thread only; 0 elsewhere or for a dead pawn. |
| `get_bullet_resist_frac` | `:get_bullet_resist_frac() -> number` | safe | Bullet resist as a fraction (0.30 = 30%). Not clamped: negative under resist shred. Game thread only; 0 elsewhere or for a dead pawn. |
| `get_bone_pos` | `:get_bone_pos(bone_name: string) -> Vector3\|nil` | safe | Bone position by name. In render callbacks, this frame's drawn pose with no skeleton solve: nil until the pawn is in the screen frame (the first call asks for it, ready from the next frame). Elsewhere, the aim set's bone, else a skeleton solve. nil for a dead pawn, a bone the model does not have, or one with no position yet. |
| `get_animgraph_symbols` | `:get_animgraph_symbols() -> string[]\|nil` | safe | PRIMARY light-vs-heavy melee tell: the broadcast animgraph SYMBOL strings (networked CGlobalSymbol array). The melee action/state string appears here — melee_charging (HEAVY windup, earliest), melee_heavy (heavy swing), melee_light1/melee_light2 (LIGHT), melee_ground_dashing/melee_air_dashing. index<->slot preserved ("" for a null slot); nil if not live/ready. Game-thread only. Read-only. |
| `get_animgraph_params` | `:get_animgraph_params() -> table\|nil` | safe | Full DUMP of every enemy-readable animgraph array plus chain diagnostics: { bools:boolean[], bytes:integer[], uint16s:integer[], ints:integer[], uints:integer[], uint64s:integer[], floats:number[], vectors:Vector3[], symbols:string[], bool_count_netvar:integer, poseRecipeSize:integer, sequence:integer, playbackRate:number, seqStart:number, dbg_str:string } or nil. FULLY schema-driven: every field offset comes from the live CSchemaSystem, RE fallback only if the schema returns 0. bools are bit-packed at the source. poseRecipeSize/playbackRate non-zero on an animating pawn confirm the chain reached CBaseAnimGraphController; dbg_str lists each field's resolved offset + whether it came from schema or fallback (fallback = unverified). Game-thread only. Read-only. SECURITY SWEEP (2026-07-26): dbg_str embeds a raw process address and is redacted to "" for untrusted (unvouched) callers; every other field carries no address and stays open to everyone. |
| `get_animgraph_param` | `:get_animgraph_param(kind: string, index: integer) -> boolean\|integer\|number\|Vector3\|string\|nil` | safe | One scalar from the animgraph arrays. kind is one of "bool"\|"byte"\|"uint16"\|"int"\|"uint"\|"uint64"\|"float"\|"vector"\|"symbol"; index is 1-based. nil if out of range / not ready. |
| `get_animgraph_states` | `:get_animgraph_states() -> {vtable_off:integer, active:integer, count:integer, transitioning:boolean, id:integer}[]\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): enumerates every CNmStateMachineNode reached via a BOUNDED, SEH-guarded, canonical-pointer-gated scan from the pawn's CAnimationGraphInstance (chain: body+m_CBodyComponent -> ctrl+m_animationController -> +m_pAnimGraphInstance). vtable_off is the matched CNmStateMachineNode vtable's module-relative RVA (client.dll 0x27E2CF0 or animationsystem.dll 0x64A880) confirming identification; active is the +0x628 int16 active-state index (-1=invalid) — the candidate light-vs-heavy melee discriminator under test; count is the +0x28 declared state count (bounds for active); transitioning is +0x620!=0 (mid-blend); id is the node's raw heap address low-32 bits for cross-tick tracking. Nodes are returned in stable ascending-address order, capped at 32. Game-thread only, one-shot (not a hot path). Read-only. |
| `get_animgraph_dbg` | `:get_animgraph_dbg() -> string` | privileged | DIAGNOSTIC companion to get_animgraph_states: runs the SAME body->ctrl->agi chain walk but ALWAYS returns the accumulated debug string (never nil) — resolved bodyOff/ctrlOff/agiOff with /schema or /fallback tags, the model-loaded precondition result, the ctrl address, and the RAW pointer value read at ctrl+agiOff printed as 0x%016llX (even when implausible, unlike get_animgraph_states which just says nil). Use this to see exactly where/why the states walk bails. Never wired into any feature. Game-thread only. Read-only. SECURITY SWEEP (2026-07-26): gated behind "schema.raw_read" (trusted-only) — the whole return value is a raw process address dump; untrusted callers get "denied". |
| `get_animgraph_dump` | `:get_animgraph_dump() -> table\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): dumps the AG2 pose-recipe blob and a handful of netvars counts using HARDCODED CLIENT-SCOPE offsets (NOT GetSchemaOffset() — this specific chain has been observed to resolve to a mixed client/server scope). Returns { recipeSize:integer, recipeVecCount:integer, recipe:string, symCnt_vec:integer, symCnt_field:integer, syms:string[], boolCnt_vec:integer, floatCnt_vec:integer, intCnt_vec:integer } or nil. recipeSize is m_nSerializePoseRecipeSizeAG2 (ctrl+0x1888); recipeVecCount is the recipe blob's own CUtlVector count (ctrl+0x1870); recipe is lowercase hex of the first up to 64 raw blob bytes (for eyeballing light-vs-heavy diffs — see the recipe-format RE notes for the byte layout); symCnt_vec/boolCnt_vec/floatCnt_vec/intCnt_vec are each array's own declared count (netvars+0xE0/0x08/0x98/0x50); symCnt_field is whichever of the four adjoining netvars+0x1E8/0x1EC/0x1F0/0x1F4 scalars numerically matches symCnt_vec (-1 if none do — only the 0x1E8 slot, m_nBoolVariablesCount, is schema-confirmed); syms is up to 16 SafeCStr-decoded symbol strings. Game-thread only. Read-only. |
| `get_graph_params` | `:get_graph_params() -> table\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): hunts for the CCitadelPlayerPawn_GraphController2 object (analog of CS2's CCSPlayerAnimationState) and scans it for CAnimGraph2ParamRefBase<T> blocks bound to known animgraph params — hero_action_is_instant (melee light/heavy discriminator candidate, instant=LIGHT), hero_action, base_state, hero_state, base_action, hero_action_is_alt_cast, movement_type, flinch. Tries base="ctrl" (CBaseAnimGraphController, body+0x4D0) first, then a bounded qword-value scan of pawn/body/ctrl for an EMBEDDED object whose own vtable ptr equals the resolved GraphController2 vtable (client.dll base + RVA 0x235e358) — candidates labeled "graphctrl2@<region>+0x<off>". Each candidate is then scanned 0x00..0x600 for ParamRef blocks (qword name-ptr matching a known param name). Returns { base:string, found:{ {name:string, cand:string, off:integer, idx:integer, bound:boolean, hex:string}[] }, tried:{ {base:string, hits:integer}[] } } or nil. found[].hex is the block's raw 0x20 bytes (wider than the documented 0x18-byte ParamRef) as lowercase hex, so a cached VALUE past the documented fields is visible without a second RE pass. Does NOT resolve a live value via idx — that needs a separate unresolved chain into the owning CAnimationGraphInstance. Game-thread only, one-shot (not a hot path). Read-only. |
| `get_instant_cast` | `:get_instant_cast() -> {pctrl:integer, vtbl_ok:boolean, bound:boolean, idx:integer, gi_nonnull:boolean, value:integer}\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): reads the m_InstantCast animgraph param LIVE VALUE (<-> "hero_action_is_instant", TRUE=instant/LIGHT melee, FALSE=charged/HEAVY) via a NEWLY-RE'd chain that SUPERSEDES the pawn+0x30->+0x4D0 CBaseAnimGraphController path used by every other animgraph reader here (that path reaches the WRONG similarly-named class for this field). Chain: pawn+0x830 DEREF -> pCtrl (the CCitadelPlayerPawn_GraphController2 instance) -> pCtrl+0x1F8 = m_InstantCast ParamRef record (CGlobalSymbol@+0, cached graph-instance ptr@+8, int16 m_nParamIndex@+0x10, bool m_bBound@+0x13) -> if bound: graphInstance=*(record+8) -> descArray=*(graphInstance+0x10) -> pDesc=descArray[idx] -> vcall pDesc's vtable slot 9 (offset +72, resolved directly off pDesc) with (pDesc, graphInstance+0x40, &out) writing the bool into out. Returns pctrl (low32 of pCtrl, 0 if null), vtbl_ok (pCtrl's vtable == client.dll+0x235E348, sanity-only), bound/idx/gi_nonnull (raw ParamRef record fields), and value (0/1 if the vcall succeeded, -1 if not bound / gi null / vcall guarded-faulted). Returns a table (not nil) even when pCtrl is null or the param is unbound — nil is reserved for a hard fault. Game-thread only, one-shot. Read-only. |
| `get_melee_state` | `:get_melee_state() -> {charging:boolean, is_heavy:boolean, state?:integer, type?:integer, start_time?:number}\|nil` | safe | DEPRECATED: use HERO_LIB.is_heavy_melee_charging(pawn) for enemies and HERO_LIB.melee_state(pawn) for the local player. Local pawn: { state (EMeleeHold_AttackState), type (EMeleeHold_AttackType), start_time, is_heavy, charging } from its HoldMelee ability. Any other pawn: { is_heavy, charging } only, from the modifier state mask, because the HoldMelee fields are networked to the owner alone. nil for a dead pawn. CHANGED: the old raw anim-graph blob fields (size, vec_count, dumped, raw_hex, hash, string state, is_light) are gone. |
| `get_trace` | `:get_trace(...: any) -> Vector3\|nil` | safe |  |
| `get_attachment` | `:get_attachment(name: string) -> Vector3\|nil` | safe |  |
| `visible` | `:visible() -> boolean` | safe |  |
| `is_visible` | `:is_visible() -> boolean` | safe | Traced line of sight from the local eye, from the tick snapshot; an ally's value can be up to 3 ticks old. |
| `has_modifier_state` | `:has_modifier_state(state: integer) -> boolean` | safe | Modifier-state bit from the tick snapshot (can lag one tick); a dead or dormant pawn reads all clear. |
| `has_modifier` | `:has_modifier(name: string) -> boolean` | safe |  |
| `matches_predicates` | `:matches_predicates(...: string\|integer) -> boolean` | safe | Every argument must hold. A string is a comma-separated slug list in the shared pred:/group:/state:/mod:/flag: vocabulary and holds if ANY slug matches; an integer is an EModifierState ordinal that must be enabled. A mod: slug containing '/' is an exact (case-insensitive) modifier name; a bare fragment is a substring. CHANGED: string arguments used to always return false. |
| `has_particle` | `:has_particle(path: string) -> boolean` | safe |  |
| `has_any_particle` | `:has_any_particle(...: string\|string[]) -> boolean` | safe | Any substring matches a particle recently created on this pawn. Accepts EITHER varargs strings `has_any_particle("a","b")` OR an array table `has_any_particle({"a","b"})` — both shapes work on every has_any_particle binding. No args => any recent particle at all. For anything TIMING-sensitive use get_particle_age instead: this stays true for the tracker's full 3s TTL. |
| `get_particle_age` | `:get_particle_age(...: string\|string[]) -> number\|nil` | safe | Seconds since the FRESHEST matching particle was created on this pawn, or nil if none is within the tracker's ~3s TTL. No args => age of the most recent particle of any path. Use this over has_any_particle whenever the question is a timing one (e.g. 'is this windup still live?'), since the boolean cannot distinguish a charge starting now from one that finished 3 seconds ago. |
| `get_abilities` | `:get_abilities() -> Ability[]` | safe |  |
| `get_ability` | `:get_ability(name_or_slot: string\|integer) -> Ability\|nil` | safe | A string resolves an ability by class name (FUZZY substring match — e.g. "citadel_ability_melee" also matches CCitadel_Ability_MeleeParry). An integer is an EAbilitySlots_t slot, same as get_ability_by_slot. For items use HERO_LIB.owned_item(record name): an item's class name is its vdata _class, which many items share. |
| `get_ability_exact` | `:get_ability_exact(class: string) -> Ability\|nil` | safe | Resolve an ability by EXACT binding-class name (byte-for-byte), avoiding get_ability's fuzzy substring match. |
| `get_ability_by_slot` | `:get_ability_by_slot(slot: integer) -> Ability\|nil` | safe | The ability the game put in this EAbilitySlots_t slot (matched on m_eAbilitySlot): signatures 0..3, active items 4..7, primary weapon 21. nil outside 0..22 or when the slot is empty. CHANGED: used to index the ability vector, whose order is not the slot order. |
| `get_signature_ability` | `:get_signature_ability(index: integer) -> Ability\|nil` | safe | Signature ability by 0-based index (0..3 = ability 1..4), resolved by slot. The index is clamped to 0..3. |
| `get_item` | `:get_item(index: integer) -> Ability\|nil` | safe | Active item by 0-based index (0..3 = item slots 4..7), resolved by slot. nil outside 0..3. |
| `get_items` | `:get_items() -> Ability[]` | safe | Every ability whose vdata type is Item, passive items included, in the pawn's ability-vector order. |
| `get_weapon` | `:get_weapon() -> Ability\|nil` | safe | The primary weapon (slot 21). Same as get_primary_weapon. |
| `get_bone_position` | `:get_bone_position(bone: string\|integer) -> Vector3` | safe | Bone position by name (the same source as get_bone_pos, so (0,0,0) in render callbacks until the pawn is in the screen frame) OR by integer index into the resolved-bone list (a skeleton solve). Returns Vector3(0,0,0) on unknown name, out-of-range index, non-finite result, or dormant pawn. `get_bone_pos(name)` remains as a name-only convenience. |
| `get_modifiers` | `:get_modifiers() -> Modifier[]` | safe |  |
| `get_modifier` | `:get_modifier(name: string) -> Modifier\|nil` | safe |  |
| `is_dormant` | `:is_dormant() -> boolean` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_address` | `:get_address() -> integer` | safe |  |
| `get_angles` | `:get_angles() -> Vector3` | safe | Eye angles from the tick snapshot (can lag one tick). |
| `get_primary_weapon` | `:get_primary_weapon() -> Ability\|nil` | safe | The ability in the primary-weapon slot (21). CHANGED: used to return the first ability-vector entry. |
| `get_currency` | `:get_currency(...: any) -> integer` | safe |  |
| `get_account_id` | `:get_account_id() -> integer` | safe | The controlling player's 64-bit Steam id (m_steamID), from the controller's row in the tick snapshot (can lag one tick), else a live controller read. 0 if no controller owns this pawn. |
| `get_hero_id` | `:get_hero_id() -> integer` | safe | Raw hero id of the controlling player, from the controller's row in the tick snapshot (can lag one tick), else a live controller read. 0 if no controller owns this pawn. |
| `get_hero_name` | `:get_hero_name() -> string` | safe | Hero name for get_hero_id (same source, can lag one tick). "" if no controller owns this pawn. |
| `get_vdata` | `:get_vdata() -> raw_struct\|nil` | privileged |  |
| `get_bones` | `:get_bones() -> table` | safe |  |
| `get_skeleton_instance` | `:get_skeleton_instance() -> integer` | privileged |  |
| `get_min_fov_to_bones` | `:get_min_fov_to_bones(cam: Vector3, yaw_only?: boolean) -> number` | safe |  |
| `get_fireport_position` | `:get_fireport_position() -> Vector3` | safe |  |
| `get_model_name` | `:get_model_name() -> string` | safe |  |
| `get_particles` | `:get_particles() -> string[]` | safe | DISTINCT particle paths recently created on this pawn (within the tracker's ~3s TTL), oldest first. A path that re-spawns is refreshed in place rather than duplicated, so this lists what is recently live — not a spawn log. Empty if none / not live. |
| `get_particle_position` | `:get_particle_position(...: any) -> Vector3\|nil` | safe |  |
| `get_hitboxes` | `:get_hitboxes() -> table[]` | safe | Per-hitbox list: { center, bone_pos, mins, maxs, radius, capsule_a, capsule_b, capsule_radius, bone_index, shape } (no name field). From this tick's aim set: {} for a pawn outside it, which joins from the next tick while scripts ask (allies included). Always {} for the local pawn. |
| `get_bbox` | `:get_bbox() -> table\|nil` | safe | Axis-aligned bounding box { mins, maxs } (plus world / screen sub-tables). |
| `get_bounding_box` | `:get_bounding_box() -> table\|nil` | safe | Native screen-space bounding rect { x, y, w, h } (C_BaseModelEntity::GetBoundingBox) - NOT the same as get_bbox. |
| `closest_hitbox_point_to_ray` | `:closest_hitbox_point_to_ray(origin: Vector3, dir: Vector3) -> table\|nil` | safe | Closest hitbox-surface point to a ray, over the same hitboxes as get_hitboxes: nil for a pawn outside this tick's aim set, and always nil for the local pawn. |
| `set_glow` | `:set_glow(color: Color, mode?: number, width?: number) -> boolean` | safe | Enable entity glow (see GlowMode). |
| `clear_glow` | `:clear_glow() -> boolean` | safe | Disable entity glow. |
| `get_player_name` | `:get_player_name() -> string` | safe | Display name of the controlling player, from the controller's row in the tick snapshot (can lag one tick), else a live controller read; "" if no controller owns this pawn (e.g. a target dummy) or not live. |
| `get_controller` | `:get_controller() -> Entity\|nil` | safe | This pawn's owning CCitadelPlayerController as a generic Entity (read any controller schema field / :get_raw_struct); nil if none or not live. |
| `__index` | `:__index(key: string) -> any` | privileged | Dynamic fallback after named methods: an m_*-prefixed key reads the live schema field off the pawn's runtime class + inheritance chain, typed by the m_ name heuristic (m_iTeamNum special-cased uint8). Unknown -> nil. This is how scripts read arbitrary networked fields (pawn.m_iHealth, pawn.m_vecAbsOrigin). |
| `get_selected_ability` | `:get_selected_ability() -> Ability\|nil` | safe | The ability the pawn has selected and waits to confirm with Fire (CCitadelAbilityComponent::m_hSelectedAbility); for the local pawn from the shared action record. nil when none is selected. |
| `is_visible_entity` | `:is_visible_entity(target: Entity) -> boolean` | safe | One sight ray from this pawn's eye to the target (a pawn's eye, else the middle of its collision box, else its origin), passing through this pawn; a hit on the target counts as seen. Game thread (cached per tick); on the render thread last tick's answer; false elsewhere, before the first answer, and for the pawn itself. |
| `get_subclass_name` | `:get_subclass_name() -> string\|nil` | safe | The hero's vdata record name ("hero_inferno"), the HERO_LIB.hero_abilities key; nil for a non-hero pawn or a hero this build does not list. |
| `get_ability_by_id` | `:get_ability_by_id(id: integer) -> Ability\|nil` | safe | The pawn's ability or item whose subclass token is `id` (utils.subclass_id of its vdata name). |
| `has_item_by_id` | `:has_item_by_id(id: integer) -> boolean` | safe | The pawn owns an item whose subclass token is `id`. |
| `get_weapon_info` | `:get_weapon_info() -> table\|nil` | safe | The primary weapon's Ability:get_weapon_info(). |
| `has_modifier_by_id` | `:has_modifier_by_id(id: integer) -> boolean` | safe | The pawn carries a modifier whose runtime name has string token `id` (utils.subclass_id of the name). Any thread. A name no frame pawn has carried yet is not known, so it answers false. |
| `get_modifier_by_id` | `:get_modifier_by_id(id: integer) -> Modifier\|nil` | safe | The modifier whose runtime name has string token `id`. Game thread, like get_modifier. |
| `get_modifier_by_id_from` | `:get_modifier_by_id_from(caster: Entity\|integer, id: integer) -> Modifier\|nil` | safe | The modifier with token `id` applied by `caster` (an entity or its handle). Game thread. |
| `has_any_modifier_state` | `:has_any_modifier_state(...: integer) -> boolean` | safe | Any of the EModifierState numbers is on for the pawn. |
| `get_modifier_state_remaining_duration` | `:get_modifier_state_remaining_duration(state: integer, caster?: Entity\|integer) -> number` | safe | The longest time left (seconds) on a modifier that enables `state`, optionally only those applied by `caster` (an entity or a handle); 0 when none is timed. Game thread; 0 elsewhere. |
| `has_active_particle` | `:has_active_particle(path: string) -> boolean` | safe | As Entity:has_active_particle. |
| `get_collision_bounds` | `:get_collision_bounds() -> Vector3, Vector3\|nil` | safe | As Entity:get_collision_bounds. |

### Entity

`usertype` · tier `safe` — Generic game entity handle (shared read/glow surface with PlayerPawn). Its tick-rate reads come from the per-tick entity frame, like PlayerPawn's; get_velocity on a soul returns the derived motion estimate. `a == b` is true for two handles of the same game instance.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe | True if this entity handle is still live/resolvable (O(1) live-set membership check). |
| `get_address` | `:get_address() -> integer` | safe | Raw entity pointer as an integer (identity key / debug). |
| `get_index` | `:get_index() -> integer` | safe | Entity entry index (slot); -1 if not live. Same value as PlayerPawn:get_index(). |
| `get_handle` | `:get_handle() -> integer\|nil` | safe | Full raw CHandle value (entry index + SERIAL bits); nil when not live. Identical in meaning to PlayerPawn:get_handle(). Use as a cache key when you need ENTITY IDENTITY: the serial makes a recycled entry slot a DIFFERENT key (cache miss) rather than a wrong hit on the dead occupant. CHANGED: the not-live return was 0, which is TRUTHY in Lua, so `if not h` never fired and every dead entity collided on key 0; it is now nil. The live VALUE is unchanged. |
| `get_class_name` | `:get_class_name() -> string` | safe | Real runtime schema class name (e.g. C_CitadelProjectile, CNPC_TrooperNeutral, CCitadelPlayerController); empty string if not live. |
| `get_raw_struct` | `:get_raw_struct() -> raw_struct\|nil` | privileged | raw_struct over this entity's address + real runtime class chain, to read/write any schema field by name; nil if not live. SECURITY SWEEP (2026-07-26): gated behind "schema.raw_read" (trusted-only). |
| `as_pawn` | `:as_pawn() -> PlayerPawn\|nil` | safe | Upgrade this generic Entity to the rich PlayerPawn usertype if it is a Citadel player pawn, else nil. |
| `get_bbox` | `:get_bbox() -> table\|nil` | safe | Axis-aligned bounding box { mins, maxs } (plus world / screen sub-tables). |
| `get_bounding_box` | `:get_bounding_box() -> table\|nil` | safe | Native screen-space bounding rect { x, y, w, h } (C_BaseModelEntity::GetBoundingBox) - NOT the same as get_bbox. |
| `get_hitboxes` | `:get_hitboxes() -> table[]` | safe | Per-hitbox list: { center, bone_pos, mins, maxs, radius, capsule_a, capsule_b, capsule_radius, bone_index, shape } (no name field). Player pawns only, as PlayerPawn:get_hitboxes (this tick's aim set; always {} for the local pawn); {} for any other entity. |
| `set_glow` | `:set_glow(color: Color, mode?: number, width?: number) -> boolean` | safe | Enable entity glow (see GlowMode). |
| `clear_glow` | `:clear_glow() -> boolean` | safe | Disable entity glow. |
| `has_particle` | `:has_particle(substr: string) -> boolean` | safe | A particle whose path contains `substr` was recently created on this entity (shared recent-particle tracker; works for ANY entity — Guardian NPC, soul, projectile). A 'recently created' signal, not a 'currently playing' scan. |
| `has_any_particle` | `:has_any_particle(...: string\|string[]) -> boolean` | safe | Any substring matches a particle recently created on this entity. Accepts EITHER an array table `has_any_particle({"a","b"})` OR varargs strings `has_any_particle("a","b")` — both shapes work on every has_any_particle binding. Empty/no args => any recent particle at all. For anything TIMING-sensitive use get_particle_age instead: this stays true for the tracker's full 3s TTL. |
| `get_particle_age` | `:get_particle_age(...: string\|string[]) -> number\|nil` | safe | Seconds since the FRESHEST matching particle was created on this entity, or nil if none is within the tracker's ~3s TTL. No args => age of the most recent particle of any path. Use this over has_any_particle whenever the question is a timing one (e.g. 'is this windup still live?'), since the boolean cannot distinguish an effect starting now from one that finished 3 seconds ago. |
| `get_particles` | `:get_particles() -> string[]` | safe | DISTINCT particle paths recently created on this entity (within the tracker's ~3s TTL), oldest first. A path that re-spawns is refreshed in place rather than duplicated, so this lists what is recently live — not a spawn log. Empty if none / not live. |
| `get_animgraph_symbols` | `:get_animgraph_symbols() -> string[]\|nil` | safe | Broadcast animgraph SYMBOL strings for any animating entity (see PlayerPawn:get_animgraph_symbols). nil for a non-animating entity. Game-thread only. Read-only. |
| `get_animgraph_params` | `:get_animgraph_params() -> table\|nil` | safe | Generic-entity animgraph dump incl. symbols (see PlayerPawn:get_animgraph_params for the shape). nil for a non-animating entity. Game-thread only. Read-only. |
| `get_animgraph_param` | `:get_animgraph_param(kind: string, index: integer) -> boolean\|integer\|number\|Vector3\|string\|nil` | safe | One scalar from the animgraph arrays (see PlayerPawn:get_animgraph_param). kind is "bool"\|"byte"\|"uint16"\|"int"\|"uint"\|"uint64"\|"float"\|"vector"\|"symbol"; index is 1-based. |
| `get_animgraph_states` | `:get_animgraph_states() -> {vtable_off:integer, active:integer, count:integer, transitioning:boolean, id:integer}[]\|nil` | safe | Generic-entity twin of PlayerPawn:get_animgraph_states (see that entry for field meanings) — reuses the same bounded, SEH-guarded CNmStateMachineNode scan. nil for a non-animating entity. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only, one-shot. Read-only. |
| `get_animgraph_dbg` | `:get_animgraph_dbg() -> string` | privileged | Generic-entity twin of PlayerPawn:get_animgraph_dbg — same chain-walk debug string, ALWAYS returned (never nil). Read-only. SECURITY SWEEP (2026-07-26): gated behind "schema.raw_read" (trusted-only) — untrusted callers get "denied". |
| `get_animgraph_dump` | `:get_animgraph_dump() -> table\|nil` | safe | Generic-entity twin of PlayerPawn:get_animgraph_dump (see that entry for the full field breakdown) — same hardcoded-client-scope AG2 pose-recipe blob + netvars-count dump. nil for a non-animating entity. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only. Read-only. |
| `get_graph_params` | `:get_graph_params() -> table\|nil` | safe | Generic-entity twin of PlayerPawn:get_graph_params (see that entry for the full field breakdown) — same GraphController2/ctrl candidate-base scan for CAnimGraph2ParamRefBase<T> blocks (hero_action_is_instant and friends). nil for a non-animating entity. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only, one-shot. Read-only. |
| `get_instant_cast` | `:get_instant_cast() -> {pctrl:integer, vtbl_ok:boolean, bound:boolean, idx:integer, gi_nonnull:boolean, value:integer}\|nil` | safe | Generic-entity twin of PlayerPawn:get_instant_cast (see that entry for the full chain + field breakdown) — reuses the same pawn+0x830->ctrl+0x1F8 ParamRef + vtbl-slot-9 vcall chain. Returns a table even when pCtrl is null/unbound; nil only on a hard fault. auto_parry reads enemies through the Entity path, not PlayerPawn, so this mirror is what makes the chain testable there. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only, one-shot. Read-only. |
| `get_melee_state` | `:get_melee_state() -> {charging:boolean, is_heavy:boolean, state?:integer, type?:integer, start_time?:number}\|nil` | safe | DEPRECATED generic-entity twin of PlayerPawn:get_melee_state (same table shape). For enemies use HERO_LIB.is_heavy_melee_charging(pawn). nil when the entity is not live. |
| `GetLocalPlayer` | `GetLocalPlayer() -> PlayerPawn\|nil` | safe | Static (global Entity table): the local player's pawn. |
| `GetAllPlayers` | `GetAllPlayers() -> PlayerPawn[]` | safe | Static: every player pawn (same enumeration as entity_list.players). |
| `GetPlayerByIndex` | `GetPlayerByIndex(index: integer) -> PlayerPawn\|nil` | safe | Static: same function as entity_list.by_index. |
| `GetEntityByIndex` | `GetEntityByIndex(index: integer) -> Entity\|nil` | safe | Static: same function as entity_list.entity_by_index. |
| `GetOrigin` | `GetOrigin(e: Entity) -> table` | safe | Static: { x, y, z } origin, the tick snapshot (this frame's drawn position in a render callback, like get_origin); {} for nil. |
| `IsAlive` | `IsAlive(e: Entity) -> boolean` | safe | Static: same function as entity_list.is_alive. |
| `GetTeam` | `GetTeam(e: Entity) -> integer` | safe | Static: team number from the tick snapshot (can lag one tick); 0 for nil. |
| `GetEyePosition` | `GetEyePosition(e: Entity) -> table` | safe | Static: { x, y, z } eye of a player pawn from the tick snapshot (origin + view offset when usable, else the origin); {} for anything else. |
| `GetClassName` | `GetClassName(e: Entity) -> string` | safe | Static: same function as entity_list.get_class. |
| `GetEntityIndex` | `GetEntityIndex(e: Entity) -> integer` | safe | Static: same function as entity_list.get_entity_index. |
| `__index` | `:__index(key: string) -> any` | privileged | Dynamic: an m_*-prefixed key resolved against this entity's REAL runtime class chain and decoded at its TRUE schema width/type (ints/floats at real width, Vector, CHandle, full 8-byte pointers, char*/CUtlString as strings, Elem[N] and CUtlVector<Elem> as 1-based tables, pointer-to-class as a nested raw_struct). Non-string/unknown/unresolved -> nil. |
| `__newindex` | `:__newindex(key: string, value: any) -> nil` | privileged | Dynamic write-through to an m_*-prefixed schema field on this entity's class chain, typed at the field's TRUE width (a uint8/int16 write no longer clobbers neighbouring bytes); unresolved/unreadable/string/nested -> silent no-op. |
| `get_modifier_by_id` | `:get_modifier_by_id(id: integer) -> Modifier\|nil` | safe | The modifier whose runtime name has string token `id`, as PlayerPawn:get_modifier_by_id, for any entity (troopers' wave buffs included). Game thread. |
| `has_active_particle` | `:has_active_particle(path: string) -> boolean` | safe | An effect with exactly this path (any case) is alive on the entity: created and not yet stopped or released. Any thread. The first call after ~10 s with no particle query or handler sees the effects created from then on. |
| `get_collision_bounds` | `:get_collision_bounds() -> Vector3, Vector3\|nil` | safe | The entity-space collision box (mins, maxs): the frame's bounds row, else the live collision property. nil when the entity has none or an empty one. No screen projection (get_bbox has that). |
| `get_vdata` | `:get_vdata() -> table\|nil` | safe | A read-only schema view of the entity's subclass vdata (vdata.m_flVaultMiniGameTime); the vdata object's own class when the game names it, else "<binding>VData", else only the common fields. nil without vdata. PlayerPawn:get_vdata keeps its own meaning (raw_struct). |

### PlayerController

`usertype` · tier `safe` — Citadel player controller (the player behind a pawn). Hero id, steam id, name and net worth come from the controller's row in the per-tick entity frame (can lag one tick), else a live read.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_hero_id` | `:get_hero_id() -> integer` | safe | Raw hero id from the controller's row in the tick snapshot (can lag one tick), else a live read; 0 when not live. |
| `get_steam_id` | `:get_steam_id() -> integer` | safe | 64-bit Steam id (m_steamID) from the tick snapshot (can lag one tick), else a live read; 0 when not live. |
| `get_steam_id_string` | `:get_steam_id_string() -> string` | safe | get_steam_id as a decimal string; "" when it is 0. |
| `get_net_worth` | `:get_net_worth() -> integer` | safe | Souls collected (m_iGoldNetWorth) from the tick snapshot (can lag one tick), else a live read. |
| `get_souls` | `:get_souls() -> integer` | safe | Same value as get_net_worth. |
| `get_player_name` | `:get_player_name() -> string` | safe | Display name (m_iszPlayerName) from the tick snapshot (can lag one tick), else a live read capped at 128 bytes; "" when not live. |
| `get_name` | `:get_name() -> string` | safe | Same value as get_player_name. |
| `get_index` | `:get_index() -> integer` | safe | The controller's entity entry index (slot, no serial bits); the player slot is this minus 1. Same meaning as Entity:get_index(). |

### Modifier

`usertype` · tier `safe` — Active modifier (buff/debuff) on an entity. modifier.m_<field> reads the modifier's schema fields: its own class's when the game names it (m_flShieldHealth, ...), else CCitadelModifier's and CBaseModifier's. Game thread, like every modifier read.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `name` | `.name: string` | safe | Read-only. The runtime modifier name (nested form "<ability>/<modifier>"); same as get_name(). |
| `duration` | `.duration: number` | safe | Read-only. Total duration in seconds; same as get_duration(). |
| `stacks` | `.stacks: integer` | safe | Read-only. Current stack count; same as get_stack_count(). A build-up's fill is not a stack: use get_buildup(). |
| `valid` | `:valid() -> boolean` | safe | The modifier is still live. |
| `get_name` | `:get_name() -> string` | safe | Runtime modifier name, e.g. "ability_vampirebat_lovebites/lovebites_buildup". "" when not live. |
| `get_duration` | `:get_duration() -> number` | safe | Total duration in seconds; <= 0 for a permanent modifier. |
| `get_remaining_time` | `:get_remaining_time() -> number` | safe | Seconds left (duration minus elapsed game time), floored at 0. 0 for a permanent modifier. |
| `get_stack_count` | `:get_stack_count() -> integer` | safe | Current stack count. |
| `get_max_stack_count` | `:get_max_stack_count() -> integer` | safe | Maximum stack count. |
| `is_stackable` | `:is_stackable() -> boolean` | safe | True when the maximum stack count is above 1. |
| `is_buildup` | `:is_buildup() -> boolean` | safe | True for a build-up modifier (Love Bites, Toxic Bullets, Silence Glyph ...). Build-ups live on the TARGET as "<ability>/<...>_buildup", one per attacker. |
| `get_buildup` | `:get_buildup() -> number` | safe | Build-up fill 0..1 (stack count / 100) for a build-up modifier; 0 for any other modifier. |
| `is_disabled` | `:is_disabled() -> boolean` | safe | The modifier's m_bDisabled flag; true when the modifier is not live. |
| `get_subclass_id` | `:get_subclass_id() -> integer` | safe | The subclass token of the ability that applied the modifier (C_BaseEntity::m_nSubclassID of that ability's class); 0 when the modifier is gone. |
| `get_caster_handle` | `:get_caster_handle() -> integer\|nil` | safe | The caster's packed handle (the number entity:get_handle() returns); nil when unset. |
| `get_ability_handle` | `:get_ability_handle() -> integer\|nil` | safe | The applying ability's packed handle; nil when unset. |
| `get_last_applied_time` | `:get_last_applied_time() -> number` | safe | Game time the modifier was last (re)applied. |

### UserCmd

`usertype` · tier `safe` — Per-tick user command passed to on_createmove.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ang_camera_angles` | `.ang_camera_angles: Angle` | safe |  |
| `orig_ang_camera_angles` | `.orig_ang_camera_angles: Angle` | safe |  |
| `orig_vec_camera_position` | `.orig_vec_camera_position: Vector3\|nil` | safe |  |
| `button_state0` | `.button_state0: integer` | safe |  |
| `button_state1` | `.button_state1: integer` | safe |  |
| `button_state2` | `.button_state2: integer` | safe |  |
| `forwardmove` | `.forwardmove: number` | safe |  |
| `leftmove` | `.leftmove: number` | safe |  |
| `upmove` | `.upmove: number` | safe |  |
| `viewangles` | `.viewangles: Angle` | safe | Read-write view angles { pitch, yaw, roll } (base.viewangles). |
| `tick_count` | `.tick_count: integer` | safe | Per-command engine tick (base.client_tick). Read+write. |
| `command_number` | `.command_number: integer` | safe | Sequential command id (base.legacy_command_number). Read+write. |
| `mouse_dx` | `.mouse_dx: integer` | safe | Raw per-tick mouse X delta (base.mousedx). Read+write. |
| `mouse_dy` | `.mouse_dy: integer` | safe | Raw per-tick mouse Y delta (base.mousedy). Read+write. |
| `impulse` | `.impulse: integer` | safe | Legacy impulse command (base.impulse). Read+write. |
| `weapon_select` | `.weapon_select: integer` | safe | Weapon/ability select field (base.weaponselect). Read+write. |
| `random_seed` | `.random_seed: integer` | safe | Prediction random seed (base.random_seed). Read+write. |
| `cmd_flags` | `.cmd_flags: integer` | safe | Command flag bitfield (base.cmd_flags). Read+write. |
| `pawn_entity_handle` | `.pawn_entity_handle: integer` | safe | CHandle of the pawn this command drives (base.pawn_entity_handle). Read+write. |
| `consumed_server_angle_changes` | `.consumed_server_angle_changes: integer` | safe | Engine bookkeeping (base). Read+write. |
| `prediction_offset_ticks` | `.prediction_offset_ticks: integer` | safe | Engine bookkeeping (base.prediction_offset_ticks_x256). Read+write. |
| `buttons_pb1` | `.buttons_pb1: integer` | safe | Direct button protobuf field 1 (the field the game reads). Read+write (also mirrors raw). |
| `buttons_pb2` | `.buttons_pb2: integer` | safe | Direct button protobuf field 2 (the field the game reads). Read+write (also mirrors raw). |
| `buttons_pb3` | `.buttons_pb3: integer` | safe | Direct button protobuf field 3 (the field the game reads). Read+write (also mirrors raw). |
| `move_crc` | `.move_crc: string` | safe | READ-ONLY. Raw command CRC bytes (always empty in Deadlock; no client producer). Write not exposed — a written value has no engine producer to match. |
| `vec_camera_position` | `.vec_camera_position: Vector3\|nil` | safe | Camera position (read+write). Setter == smooth_aim: direct write, bypasses the PSilent ~150u clamp. Use set_psilent_at_pos for the clamped path. |
| `camera_roaming_speed` | `.camera_roaming_speed: number` | safe | Free-roam camera speed (outer cmd). Read+write. |
| `in_shop` | `.in_shop: boolean` | safe | Is the shop open (outer cmd). Read+write. |
| `using_free_cursor` | `.using_free_cursor: boolean` | safe | Free-cursor state (outer cmd). Read+write. |
| `is_in_third_person_view` | `.is_in_third_person_view: boolean` | safe | Third-person view state (outer cmd). Read+write. |
| `enemy_hero_aimed_at` | `.enemy_hero_aimed_at: integer` | safe | 'Who am I aimed at' hint field (outer cmd). Read+write. |
| `add_buttonstate1` | `:add_buttonstate1(bit: integer) -> nil` | safe |  |
| `add_buttonstate2` | `:add_buttonstate2(bit: integer) -> nil` | safe |  |
| `add_buttonstate3` | `:add_buttonstate3(bit: integer) -> nil` | safe |  |
| `clear_buttonstate1` | `:clear_buttonstate1(bit: integer) -> nil` | safe |  |
| `clear_buttonstate2` | `:clear_buttonstate2(bit: integer) -> nil` | safe |  |
| `clear_buttonstate3` | `:clear_buttonstate3(bit: integer) -> nil` | safe |  |
| `get_orig_button_state1` | `:get_orig_button_state1() -> integer` | safe | The down word (buttonstate1) the game produced for this CreateMove, captured before any feature or script wrote the command: what the player actually pressed. CHANGED: it is read from the CreateMove-begin snapshot; it used to read the live word when the cmd object was built, after native features and earlier handlers had written it. |
| `execute_ability_indices` | `:execute_ability_indices(mask: integer) -> nil` | safe |  |
| `smooth_aim` | `:smooth_aim(pos: Vector3) -> nil` | safe |  |
| `set_view_roll` | `:set_view_roll(roll: number) -> nil` | safe |  |
| `set_psilent_at_pos` | `:set_psilent_at_pos(pos: Vector3, reach_units: number?) -> boolean` | safe | Aim at ANY 3D world position. Optional reach_units: omit/<=0 = default clamp (~145-150u); >0 = opt-in override past ~150u (the engine hard-clamps the camera at ~150u, so it may not fully apply). false = PSilent bus busy; hold fire this tick. |
| `can_psilent_at_pos` | `:can_psilent_at_pos(pos: Vector3, reach_units: number?) -> boolean` | safe | Reachability gate for set_psilent_at_pos; pass the SAME reach_units so the gate matches the cast. |
| `set_psilent_at_entity` | `:set_psilent_at_entity(entity: PlayerPawn, reach_units: number?) -> boolean` | safe | Prioritize a SPECIFIC entity for PSilent (handle-safe, game-thread only). Optional reach_units: omit/<=0 = default clamp; >0 = opt-in override past ~150u (may not fully apply). false = stale handle / gone / bus busy. |
| `can_psilent_at_entity` | `:can_psilent_at_entity(entity: PlayerPawn, reach_units: number?) -> boolean` | safe | Reachability gate for set_psilent_at_entity; pass the SAME reach_units so the gate matches the cast. |
| `reset_camera_pos` | `:reset_camera_pos() -> nil` | safe |  |
| `reset_camera_ang` | `:reset_camera_ang() -> nil` | safe |  |
| `reset_backtrack` | `:reset_backtrack() -> nil` | safe |  |
| `disable_condition` | `:disable_condition(...: any) -> nil` | safe |  |
| `get_orig_button_state2` | `:get_orig_button_state2() -> integer` | safe | The changed-buttons word (buttonstate2) the game produced for this CreateMove, before any feature or script wrote the command. |
| `get_orig_button_state3` | `:get_orig_button_state3() -> integer` | safe | The wheel word (buttonstate3) the game produced for this CreateMove, before any feature or script wrote the command. |
| `was_button_down` | `:was_button_down(bits: integer) -> boolean\|nil` | safe | True when any of `bits` was down on the previous command, as the last Lua handler that ran on it left it. nil off the game thread or for a cmd that is not this tick's. |
| `pulse` | `:pulse(bits: integer) -> boolean\|nil` | safe | A fresh press of `bits` now (down + changed) and a forced release on the next command, which a pulse on that command cannot override. false while the bits are being released or were already pulsed on this command, so a pulse asked for every tick lands on alternate ticks and the game sees a clean edge each time. nil off the game thread or for a cmd that is not this tick's. |
| `maintain_hold` | `:maintain_hold(bits: integer)` | safe | Keeps `bits` exactly as the previous command left them, without a new edge: down ones stay down (never re-pressed), up ones stay up (a fresh player press is swallowed). Game thread, this tick's cmd only; a no-op elsewhere. |
| `aim` | `:aim(opts: table) -> integer\|nil` | safe | Aims one request for this tick through the aim paths the user's own aim runs on and returns an aim.status number. aim.type.SILENT / MAGIC_BULLETS go through the PSilent bus (applied at the end of the tick), DEFAULT through the screen-space aimbot. Every call passes the action gate (opts.role, default "offense_auto") and Safety: the PSilent cone, the visible-aim cone and smoothing floor, the reaction floor, the headshot cap for weapon shots and the script-aim hit chance. opts: aim_type (aim.type bits), what to aim at: aim_pos (Vector3), aim_angle (Angle), custom_ang_pitch / custom_ang_yaw (the current view with that pitch / yaw), or with none of these target_ent's eye point; target_ent, ability_ent (the casting ability), smooth (1..100, replaces the aim set's DEFAULT smoothing, never below Safety's floor), allowed_min_fov (DEFAULT is READY within this many degrees, default 1), max_fov (> 0: refused beyond this angle from the view), trace_pos (the shot must reach it from where it leaves), trace_radius (> 0: a hull of that half size, traced to aim_pos when there is no trace_pos), mb_only (only a camera-shifted shot reaches: no DEFAULT drive), role, on_aimed_callback() (run on READY) and on_process_callback() (run on PENDING and AIMING). A field of the wrong type is reported as a bad argument and answers INVALID. nil for a cmd that is not the one CreateMove builds now. Game thread, from on_createmove. |
| `predict_aim_camera` | `:predict_aim_camera(target: Vector3) -> Vector3\|nil` | safe | Where the command's camera stands once the view turns to look at `target`: the third-person camera orbits the eye rigidly, so turning the view moves the point the shot leaves from. nil without a live local pawn, when no view looks at `target` (it sits inside the camera's orbit), or for a cmd that is not this tick's. |
| `predict_magic_bullets_origin` | `:predict_magic_bullets_origin(target: Vector3, ability?: Ability) -> Vector3\|nil` | safe | Where a magic-bullets (PSilent) shot at `target` leaves from: the camera slid across its unchanged view until the view line meets `target`, lifted by the projectile's drop. `ability` is a projectile ability, omitted for the weapon's bullet. nil off the game thread, without a live local pawn or projectile speed, for a target behind the view or past the camera reach the PSilent commit accepts. |

### CUserCmd

`usertype` · tier `safe` — Raw SDK command handle (lighter surface than UserCmd).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `add_buttonstate1` | `:add_buttonstate1(buttons: integer) -> nil` | safe |  |
| `remove_buttonstate1` | `:remove_buttonstate1(buttons: integer) -> nil` | safe |  |
| `get_buttonstate1` | `:get_buttonstate1() -> integer` | safe |  |

### CallbackHandle

`usertype` · tier `safe` — Handle returned by callback.on_*:set(...).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set` | `:set(fn: function)` | safe | Install/replace the PRIMARY handler for this channel (last :set wins). Coexists with any :add handlers. |
| `unset` | `:unset()` | safe | Clear this channel's PRIMARY handler for the owning script (:add handlers are unaffected). |
| `add` | `:add(fn: function) -> AddedCallbackHandle` | safe | Add an ADDITIONAL handler (multiple coexist). Primary :set + every :add all fire, in registration order, each independently guarded. Returns a handle to remove just this one. |
| `remove` | `:remove(handle: AddedCallbackHandle) -> boolean` | safe | Remove an added handler previously returned by :add (alternative to handle:remove()). |

### AddedCallbackHandle

`usertype` · tier `safe` — Handle returned by callback.on_*:add(fn); :remove() deletes just that one added handler.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `remove` | `:remove() -> boolean` | safe | Delete just this added handler; leaves the primary and other added handlers untouched. One-shot. |

### MenuNode

`usertype` · tier `safe` — Menu tree node (tab/section/group/gear/leaf builder + value accessor).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Section` | `:Section(name: string, side?: integer) -> MenuNode` | safe | Optional side is an Enum.GroupSide (Left/Right) column pin. |
| `Group` | `:Group(name: string, side?: integer) -> MenuNode` | safe | Optional side is an Enum.GroupSide (Left/Right) column pin. |
| `Gear` | `:Gear(name: string, icon?: string, small?: boolean) -> MenuNode` | safe |  |
| `Create` | `:Create(name: string, side?: integer) -> MenuNode` | safe | Legacy alias for Group; optional side is an Enum.GroupSide (Left/Right) column pin. |
| `Find` | `:Find(name: string) -> MenuNode\|nil` | safe |  |
| `Switch` | `:Switch(name: string, default?: boolean, icon?: string, tooltip?: string) -> MenuNode` | safe | Trailing string args are absorbed as (icon, tooltip) in that order; the first string is the icon, not the tooltip. |
| `Slider` | `:Slider(name: string, min: number, max: number, default?: number, format?: string) -> MenuNode` | safe | Float slider. Order is (min, max, default). default defaults to min. Last arg is a printf-style FORMAT like "%.1f", NOT a tooltip (use :Tooltip()). |
| `SliderInt` | `:SliderInt(name: string, min: integer, max: integer, default?: integer, format?: string) -> MenuNode` | safe | Integer slider. Order is (min, max, default). default defaults to min. Last arg is a printf-style FORMAT like "%d", NOT a tooltip (use :Tooltip()). |
| `SliderFloat` | `:SliderFloat(name: string, min: number, max: number, default?: number, format?: string) -> MenuNode` | safe | Alias of Slider. Order is (min, max, default). default defaults to min. Last arg is a printf-style FORMAT like "%.1f", NOT a tooltip (use :Tooltip()). |
| `Combo` | `:Combo(name: string, items: string[], default?: integer, icon?: string, tooltip?: string) -> MenuNode` | safe | Trailing string args after default are absorbed as (icon, tooltip); the first string is the icon, not the tooltip. Numeric items are converted to text and cut at 47 characters. |
| `MultiCombo` | `:MultiCombo(name: string, items: string[], default_on?: string[], icon?: string, tooltip?: string) -> MenuNode` | safe | default_on is a list of item names to start enabled (all OFF if omitted). Trailing string args are absorbed as (icon, tooltip). |
| `MultiSelect` | `:MultiSelect(name: string, items: string[], default_on?: string[], icon?: string, tooltip?: string) -> MenuNode` | safe | default_on is a list of item names to start enabled (all OFF if omitted). Trailing string args are absorbed as (icon, tooltip). |
| `Bind` | `:Bind(name: string, default_key?: integer, icon?: string, tooltip?: string) -> MenuNode` | safe | default_key is an Enum.ButtonCode. Trailing string args are absorbed as (icon, tooltip); the first string is the icon, not the tooltip. |
| `ColorPicker` | `:ColorPicker(name: string, r?: number, g?: number, b?: number, a?: number) -> MenuNode` | safe | Numeric-channel (0-255) form shown; also accepts ColorPicker(name, Color) plus trailing icon?/tooltip? strings. |
| `Button` | `:Button(name: string, callback: function) -> MenuNode` | safe |  |
| `Label` | `:Label(text: string) -> MenuNode` | safe |  |
| `Input` | `:Input(name: string, default?: string) -> MenuNode` | safe | Text input. Takes only (name, default) - it has NO tooltip parameter; apply a tooltip via the separate :Tooltip() decorator. |
| `Tooltip` | `:Tooltip(text: string) -> MenuNode` | safe |  |
| `Icon` | `:Icon(icon: string) -> MenuNode` | safe |  |
| `Image` | `:Image(image: string) -> MenuNode` | safe |  |
| `SetCallback` | `:SetCallback(fn: function) -> MenuNode` | safe |  |
| `Visible` | `:Visible(v: boolean) -> MenuNode` | safe |  |
| `Remove` | `:Remove() -> boolean` | safe | Permanently unlink this node (and its descendants) from the menu tree — for probe/temporary nodes that only Visible(false) could hide before. ConfigStore values keyed by its path are kept. |
| `Disabled` | `:Disabled(v: boolean) -> MenuNode` | safe |  |
| `VisibleCondition` | `:VisibleCondition(fn: fun():boolean) -> MenuNode` | safe |  |
| `DisableCondition` | `:DisableCondition(fn: fun():boolean) -> MenuNode` | safe |  |
| `link_to_ui_visible_condition` | `:link_to_ui_visible_condition(other: MenuNode) -> MenuNode` | safe |  |
| `link_to_ui_disable_condition` | `:link_to_ui_disable_condition(other: MenuNode) -> MenuNode` | safe |  |
| `Get` | `:Get() -> any` | safe |  |
| `Set` | `:Set(value: any) -> MenuNode` | safe |  |
| `SetColor` | `:SetColor(r: number, g: number, b: number, a: number) -> MenuNode` | safe |  |
| `GetBool` | `:GetBool() -> boolean` | safe |  |
| `GetInt` | `:GetInt() -> integer` | safe |  |
| `GetFloat` | `:GetFloat() -> number` | safe |  |
| `GetString` | `:GetString() -> string` | safe |  |
| `IsDown` | `:IsDown() -> boolean` | safe |  |
| `IsPressed` | `:IsPressed() -> boolean` | safe |  |
| `IsToggled` | `:IsToggled() -> boolean` | safe |  |
| `SetToggled` | `:SetToggled(v: boolean) -> MenuNode` | safe |  |
| `Name` | `:Name() -> string` | safe |  |
| `Path` | `:Path() -> string` | safe |  |
| `ItemGrid` | `:ItemGrid(name: string, items: string[], default_on?: string[]) -> MenuNode` | safe | Icon-grid multi-select (square item/ability icon tiles); values round-trip through the MultiValue store. |
| `Hitbox` | `:Hitbox(name: string, defaults?: integer[]) -> MenuNode` | safe | Per-ability Head/Neck/Torso/Arms/Legs tri-state (off/on/priority). defaults is a {0\|1\|2} list in H/N/T/A/L order (omitted = {1,1,1,0,0}). Backing value is one int bitfield (bits 0-4 enabled, 5-9 priority) — feed :Get() to get_hitbox_aim. |
| `Add` | `:Add(item: string, ...) -> MenuNode` | safe | Append one icon-grid tile to THIS node. Returns self. |
| `ColorAttach` | `:ColorAttach(name: string, r_or_color?: number\|Color, g?: number, b?: number, a?: number) -> MenuNode` | safe | A small color swatch attached to the right of the owning switch. Numeric-channel (0-255) or Color form. |
| `EspPreview` | `:EspPreview(name: string) -> MenuNode` | safe | Valueless leaf rendering the live ESP-preview portrait panel. |
| `ThemePicker` | `:ThemePicker(name: string) -> MenuNode` | safe | Combo seeded with the shipped theme names; selection is a stored int index. |
| `CustomBind` | `:CustomBind(name: string) -> MenuNode` | safe | Valueless keybind leaf driving key+mode through the universal hotkey popup. |
| `GearMirror` | `:GearMirror(mirror: boolean) -> MenuNode` | safe | false => the cog stays visible/openable even when the owning switch is off (default true). |
| `UnsetCallback` | `:UnsetCallback(name?: string) -> MenuNode` | safe | Clears the change handler (name arg accepted and ignored). |
| `List` | `:List() -> string[]` | safe | Full option list as a 1-based array (Combo/MultiCombo/MultiSelect); empty otherwise. |
| `ListEnabled` | `:ListEnabled() -> string[]` | safe | 1-based array of currently-ON option names. |
| `key_held` | `:key_held() -> boolean` | safe | RAW physical key-down, INDEPENDENT of Toggle/Hold mode (defeats a stale Toggle latch). |
| `key_code` | `:key_code() -> integer` | safe | RAW assigned keycode (VK); 0 == unbound. |
| `is_bound` | `:is_bound() -> boolean` | safe | true iff the bind has a non-zero key. |
| `VisibleWhen` | `:VisibleWhen(node: MenuNode, value: any, negate?: boolean) -> MenuNode` | safe | The row shows while `node` holds `value` (or, negated, while it does not): a Combo's 0-based index, a Switch's boolean, a slider's number; a Multi node is matched by an item name. Evaluated natively with the page (no Lua call per frame). Alias visible_when. |
| `visible_when` | `:visible_when(node: MenuNode, value: any, negate?: boolean) -> MenuNode` | safe | Alias of VisibleWhen. |
| `RowBind` | `:RowBind() -> string\|nil, string\|nil` | safe | The bind on a Switch / Combo row (the right-click bind the native rows use): "hold" \| "toggle" \| "always" and the keycap's label; nil, nil when unbound. The first bind in the binds list wins. |

### MenuPanel

`usertype` · tier `safe` — A HUD panel placement returned by Menu.Panel.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Place` | `:Place(w: number, h: number) -> number, number, number, number` | safe | Where to draw a w x h panel this frame: x, y, scale, alpha (scale = the UI scale times the panel's own, else the HUD's; alpha = its opacity). On the render thread a dragged panel follows the drag. nil when the panel is gone. |
| `Dragging` | `:Dragging() -> boolean` | safe | The menu is dragging this panel now (render thread). |

### File

`usertype` · tier `privileged` — Open file handle (io / File API).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `read` | `:read(fmt?: string\|integer) -> string\|number\|nil` | privileged | Reads by format: "a" the rest of the file (the default; "" at the end), "l" the next line without its end of line, "L" the next line with it, "n" a number, or an integer byte count. The Lua 5.1 spellings "*a", "*l", "*n" work too. nil when no line or number is left, or for an unknown format. |
| `write` | `:write(data: string) -> boolean` | privileged |  |
| `close` | `:close()` | privileged |  |
| `is_open` | `:is_open() -> boolean` | privileged | Whether the file is still open (false after close). |
| `lines` | `:lines() -> string[]` | privileged | 1-indexed array of the remaining lines from the current cursor. |
| `seek` | `:seek(whence?: string, offset?: integer) -> integer` | privileged | Move the cursor. whence = "set"\|"cur"\|"end" (default "cur"); returns the new absolute position (-1 on failure). |
| `flush` | `:flush() -> boolean` | privileged | Flush buffered writes to disk. |

### GameEvent

`usertype` · tier `safe` — Game event (on_game_event / user-message payload).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_int` | `:get_int(key: string) -> integer` | safe |  |
| `get_float` | `:get_float(key: string) -> number` | safe |  |
| `get_string` | `:get_string(key: string) -> string` | safe |  |
| `get_bool` | `:get_bool(key: string) -> boolean` | safe |  |
| `get_name` | `:get_name() -> string` | safe |  |

### raw_struct

`usertype` · tier `privileged` — Typed read/write view over a native struct pointer.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_int` | `:get_int(field: string) -> integer` | privileged |  |
| `get_float` | `:get_float(field: string) -> number` | privileged |  |
| `get_bool` | `:get_bool(field: string) -> boolean` | privileged |  |
| `get_vec` | `:get_vec(field: string) -> Vector3` | privileged |  |
| `set_int` | `:set_int(field: string, value: integer) -> nil` | privileged |  |
| `set_float` | `:set_float(field: string, value: number) -> nil` | privileged |  |
| `set_bool` | `:set_bool(field: string, value: boolean) -> nil` | privileged |  |
| `set_vec` | `:set_vec(field: string, value: Vector3) -> nil` | privileged |  |
| `offset_of` | `:offset_of(field: string) -> integer` | privileged |  |
| `class_name` | `:class_name() -> string` | privileged |  |
| `address` | `:address() -> integer` | privileged |  |
| `__index` | `:__index(field: string) -> any` | privileged | Read a schema field by name, typed by the m_ prefix heuristic (m_fl=float, m_b=bool, m_vec/ang/v=Vector3, m_h=handle, else int32); page-validated. Unresolved/null -> nil. |
| `__newindex` | `:__newindex(field: string, value: any) -> nil` | privileged | Write a schema field by name, typed by the m_ prefix heuristic; page-validated. Unresolved/unreadable -> silent no-op. |

### trace

`namespace` · tier `safe` — World / entity traces through the query service. Engine rays (ray, line, bullet, visible, hits_between, aim_blocked, point_contents) run on the game thread and are cached per tick. In a render callback each returns the deferred answer, the same ray traced on the last game tick, and nil before one exists. trace.hull sweeps the static map mesh from any thread.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `line` | `trace.line(start: Vector3, finish: Vector3, opts?: table) -> table` | safe | Same function as trace.ray. |
| `hull` | `trace.hull(start: Vector3, finish: Vector3, radius?: number) -> table` | safe | Sphere sweep (radius in units, default 5) against the static map mesh, any thread: { hit, fraction, position, end_pos, normal, entity = nil, is_geometry = true, material_hash }. Without a mesh for the map: a miss, no material_hash. |
| `bullet` | `trace.bullet(start: Vector3, finish: Vector3, opts?: table) -> table` | safe | Same function as trace.ray. |
| `bullet_hitbox` | `trace.bullet_hitbox(cmd_or_start: any, finish?: Vector3, opts?: table) -> table\|nil` | safe | With a Vector3 start: trace.ray. With a CUserCmd (on_createmove): a Hull ray from the command's camera along its view angles, returning { hit, bone, hitgroup, entity }; bone and hitgroup both carry the FNV-1a hash of the hit hitbox's bone name. Game thread only (elsewhere hit = false). |
| `visible` | `trace.visible(from: Vector3, to: Vector3, target?: Entity) -> boolean\|nil` | safe | Line of sight (the visibility filter); with a target, a hit on it counts as visible. In a render callback: the deferred answer (last tick's trace of the same ray), nil before one exists. Treat nil as unknown. |
| `ray` | `trace.ray(start: Vector3, finish: Vector3, opts?: table) -> table\|nil` | safe | Hull ray (the entity-bone filter): { hit, fraction, position, end_pos, normal, entity, is_geometry }. opts.skip / skip_entity / ignore names an entity the ray passes through. In a render callback: the deferred answer (last tick's trace of the same ray), nil before one exists. |
| `is_visible` | `trace.is_visible(from: Vector3, to: Vector3, target?: Entity) -> boolean\|nil` | safe | Same function as trace.visible. |
| `point_contents` | `trace.point_contents(pos: Vector3) -> integer\|nil` | safe | Contents bits at a point (1 = solid, 0x20 = water). In a render callback: the deferred answer, nil before one exists. |
| `contents_between` | `trace.contents_between(a: Vector3, b: Vector3) -> integer\|nil` | safe | point_contents(a) \| point_contents(b); nil while either has no answer yet. |
| `hits_between` | `trace.hits_between(start: Vector3, finish: Vector3, opts?: table) -> boolean\|nil` | safe | true when the world or an entity other than opts.skip blocks the Hull ray; true for a bad vector. In a render callback: the deferred answer (last tick's trace of the same ray), nil before one exists. |
| `aim_blocked` | `trace.aim_blocked(start: Vector3, target: Vector3, opts?: table) -> boolean\|nil` | safe | true unless the Hull ray is clear (player pawns and opts.skip do not block); true for a bad vector. In a render callback: the deferred answer (last tick's trace of the same ray), nil before one exists. |
| `build_filter` | `trace.build_filter(spec: table) -> userdata\|nil` | safe | trace.cast's spec table read once and kept, with its should_hit, for every trace.cast that gets it: an opaque TraceFilter, nil for anything but a table. |
| `mask` | `.mask: table` | safe | Contents mask constants (SOLID, PLAYER, SHOT, VISIBLE, WINDOW, WATER, HITBOX, ...). |
| `cast` | `trace.cast(start: Vector3, finish: Vector3, filter?: table\|userdata, radius_or_mins?: number\|Vector3, maxs?: Vector3) -> table\|nil` | safe | One engine trace with a script filter: a line, a sphere (a radius) or a box (mins, maxs). filter = { bullet (true starts from the game's own bullet filter for a bullet the local hero fires), mask, exclude, interacts_as, objects, group, skip (an entity; false for none; omitted = the local pawn), should_hit = function(entity) -> boolean } or a trace.build_filter result; named fields override the bullet values. { hit, fraction, start_solid, position, entity, is_geometry, hitgroup, ... }. Game thread; nil elsewhere and when the engine cast does not run. NEW this round: the `bullet` key. |

### mem

`namespace` · tier `privileged` — Raw memory access (read/write/scan/call).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `read_int` | `mem.read_int(address: integer) -> integer\|nil` | privileged |  |
| `read_int64` | `mem.read_int64(address: integer) -> integer\|nil` | privileged |  |
| `read_float` | `mem.read_float(address: integer) -> number\|nil` | privileged |  |
| `read_double` | `mem.read_double(address: integer) -> number\|nil` | privileged |  |
| `read_bool` | `mem.read_bool(address: integer) -> boolean\|nil` | privileged |  |
| `read_byte` | `mem.read_byte(address: integer) -> integer\|nil` | privileged |  |
| `read_ptr` | `mem.read_ptr(address: integer) -> integer\|nil` | privileged |  |
| `read_vec3` | `mem.read_vec3(address: integer) -> Vector3\|nil` | privileged |  |
| `read_string` | `mem.read_string(address: integer, max_len?: integer) -> string\|nil` | privileged |  |
| `write_int` | `mem.write_int(address: integer, value: integer) -> boolean` | privileged |  |
| `write_int64` | `mem.write_int64(address: integer, value: integer) -> boolean` | privileged |  |
| `write_float` | `mem.write_float(address: integer, value: number) -> boolean` | privileged |  |
| `write_double` | `mem.write_double(address: integer, value: number) -> boolean` | privileged |  |
| `write_bool` | `mem.write_bool(address: integer, value: boolean) -> boolean` | privileged |  |
| `write_byte` | `mem.write_byte(address: integer, value: integer) -> boolean` | privileged |  |
| `write_ptr` | `mem.write_ptr(address: integer, value: integer) -> boolean` | privileged |  |
| `write_vec3` | `mem.write_vec3(address: integer, value: Vector3) -> boolean` | privileged |  |
| `write_string` | `mem.write_string(address: integer, value: string) -> boolean` | privileged |  |
| `module_base` | `mem.module_base(module_name: string) -> integer\|nil` | privileged |  |
| `pattern_scan` | `mem.pattern_scan(module_name: string, pattern: string, offset?: integer) -> integer\|nil` | privileged |  |
| `get_call_target` | `mem.get_call_target(address: integer) -> integer\|nil` | privileged |  |
| `get_ptr_address` | `mem.get_ptr_address(address: integer, disp_offset?: integer, instr_len?: integer) -> integer\|nil` | privileged |  |
| `vfunc` | `mem.vfunc(instance: integer, index: integer) -> integer\|nil` | privileged |  |
| `call` | `mem.call(address: integer, ret_type: string, arg_types: string[], ...: any) -> any` | privileged |  |

### hooks

`namespace` · tier `privileged` — Function hooking (vmt / detour).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `vmt` | `hooks.vmt(instance: integer, slot_index: integer, detour: fun(args:table):any) -> HookHandle\|nil` | privileged |  |
| `detour` | `hooks.detour(target_addr: integer, detour: fun(args:table):any) -> HookHandle\|nil` | privileged |  |
| `subscribe` | `hooks.subscribe(hook: string, handler: function) -> (string\|nil, integer)` | privileged | callback.add on the Lua channel behind a hook name; returns the channel and the callback id (nil, 0 without a function). A name list_subscribable does not list raises an error. FrameStageNotify maps to post_framestage, OnHeroKilled to hero_killed, OnFireBullets and OnBulletCreate to bullet_create. |
| `unsubscribe` | `hooks.unsubscribe(hook: string, id: integer) -> boolean` | privileged | callback.remove of a subscribe id on the hook's channel. |
| `list_subscribable` | `hooks.list_subscribable() -> table[]` | privileged | Every hook name subscribe accepts, as { hook, channel } rows (14 rows). |
| `is_subscribable` | `hooks.is_subscribable(hook: string) -> boolean` | privileged | True when subscribe accepts the name. |
| `channel_for` | `hooks.channel_for(hook: string) -> string\|nil` | privileged | The channel subscribe would use; nil for a name it rejects. |

### HookHandle

`usertype` · tier `privileged` — Handle returned by hooks.vmt / hooks.detour.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `remove` | `:remove() -> nil` | privileged |  |
| `call_original` | `:call_original(...: integer) -> integer\|nil` | privileged |  |
| `is_active` | `:is_active() -> boolean` | privileged |  |

### Schema

`namespace` · tier `safe` — Source2 schema access (enums / field offsets).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `enum` | `Schema.enum(name: string) -> table` | safe |  |
| `fields` | `Schema.fields(class: string) -> table` | safe |  |
| `offset` | `Schema.offset(class: string, field: string) -> integer` | safe |  |
| `field_info` | `Schema.field_info(class: string, field: string) -> table\|nil` | safe | Field metadata { offset, type, ... }. |
| `read` | `Schema.read(target: integer\|PlayerPawn\|Ability\|Entity, class: string, field: string) -> any\|nil` | safe | Read a schema field off an entity. Pass the entity/pawn/ability object, or a raw address the engine handed out (ent:get_address()). Arbitrary addresses return nil unless the script is trusted. |

### prediction

`namespace` · tier `safe` — Projectile / movement prediction over the cheat's solvers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `projectile` | `prediction.projectile(ability_or_params: any, ...) -> table\|nil` | safe | With a radius (params.radius or the ability's), a lead whose path the map mesh blocks returns nil. |
| `aim_angles` | `prediction.aim_angles(eye: Vector3, target_pos: Vector3, target_vel: Vector3, speed: number, gravity: number, target_gravity?: number) -> table\|nil` | safe | target_gravity (the target's fall, units/s^2) defaults to sv_gravity, 800 on standard servers. |
| `launch_position` | `prediction.launch_position(ability: Ability) -> Vector3\|nil` | safe |  |
| `launch_angle` | `prediction.launch_angle(ability: Ability) -> table\|nil` | safe |  |
| `fastest_projectile` | `prediction.fastest_projectile() -> table\|nil` | safe |  |
| `simulate_physics` | `prediction.simulate_physics(start_pos: Vector3, start_vel: Vector3, gravity?: number, time: number, step?: number) -> table\|nil` | safe | Moves a point under gravity (default sv_gravity) for `time` s in `step` steps (default 1/64), sweeping each step against the map collision mesh (radius 18) and sliding along what it hits. Returns { end_pos, end_vel, hit_wall, hit_floor, hit_ceiling, collisions, path }. Nothing collides while the map mesh is not built. |
| `gravity` | `prediction.gravity(pawn?: PlayerPawn, distance?: number) -> number\|nil` | safe | Bullet drop of the pawn's current primary weapon in units/s^2 (m_flBulletGravityScale x sv_gravity, 800 on standard servers; 0 = no drop). The local pawn's comes from the per-tick bullet data the aimbot leads with (re-read on a weapon change and every second); another pawn's is read live. With a distance in units: the constant gravity that drops a straight shot that long as far as the weapon's gravity-by-distance curve does (Rat King's curve: no drop to ~1500 units, a 0.8 scale at 3000, so gravity(nil, 3000) is about 45); without one, the base scale. Defaults to the local pawn; nil when there is no pawn or its weapon data cannot be read. |
| `trajectory_blocked` | `prediction.trajectory_blocked(from: Vector3, to: Vector3, time?: number, gravity?: number, radius?: number, segments?: integer, near_impact_skip?: number) -> boolean` | safe | true when the map mesh blocks the shot before the last near_impact_skip of its path; arced in `segments` chords when gravity and time are set; swept with `radius` (default 5). false without a positive time; segments defaults to 4 and near_impact_skip is a 0-1 fraction of the path. |
| `simulate` | `prediction.simulate(pawn: PlayerPawn, ticks?: integer) -> Vector3[]` | safe | the pawn's path over `ticks` 1/64 s steps from this tick's origin and velocity, through simulate_physics' mesh sweep. ticks defaults to 32; empty when the frame does not hold the pawn. |

### nav

`namespace` · tier `safe` — Nav routing (grid A* over the static collision mesh).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `find_path` | `nav.find_path(start: Vector3, goal: Vector3) -> Vector3[]\|nil, string?` | safe | Request + poll: the search runs off the game thread. Returns the path once it is ready; until then nil, "pending", and nil, "no_path" when there is none (or no map mesh). The finished path is reused while the goal stays within 48 units and the start within 256 units; moving either end 48 units or more starts a new request. Each script has its own request slot. Invalid arguments return a lone nil. |
| `find_path_async` | `nav.find_path_async(start: Vector3, goal: Vector3) -> boolean` | safe | Starts a background route search for nav.get_route. Its slot is separate from find_path's and from Best Box Route's, so they do not overwrite each other. |
| `get_route` | `nav.get_route() -> Vector3[]\|nil` | safe | The route of the last find_path_async request once it is ready, else nil. |

### safety

`table` · tier `safe` — Safety mode as scripts see it, read-only: the same rule table and state native features read. Nothing here changes the mode.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `active` | `safety.active() -> boolean` | safe | True while Safety's rules apply. |
| `mode` | `safety.mode() -> string` | safe | "off" \| "automatic" \| "always". |
| `session` | `safety.session() -> string` | safe | "unknown" \| "local" \| "online". |
| `limit` | `safety.limit(slug: string\|MenuNode) -> number\|nil, number?, boolean?` | safe | lo, hi, forced while a rule limits the setting, nil otherwise. slug: a setting slug, a ui.find handle or a script option's menu path. An unlimited side reads -math.huge / math.huge. |
| `clamp` | `safety.clamp(slug: string\|MenuNode, value: number\|boolean) -> number\|boolean` | safe | The value as Safety lets it be read (a number, or a bool for a toggle). |

### action

`table` · tier `safe` — The local hero's action record and the automation gate, the same producer native features read. On the game thread inside a tick each call reads this tick's record; anywhere else the last published one. act: "move", "look", "jump", "air_jump", "dash", "air_dash", "down_dash", "slide", "mantle", "wall_jump", "zipline_boost", "melee", "heavy_melee", "parry", "shoot", "reload", "ability1".."ability4", "item1".."item4". role: "move", "offense_auto", "offense_assist", "defense", "replay". An unknown name raises an argument error.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `state` | `action.state() -> table` | safe | A fresh table of the record's named fields: context (built, in_match, alive, paused, typing, focused, game_cursor, panic, ...), movement (grounded, airborne, sliding, mantling, zipline, zipline_boost, rope, flying, air_jumps_left, air_dashes_left, dash_jump_window, ...), crowd control (cc, stunned, asleep, frozen, rooted, silenced, muted, disarmed, slow_frac, the *_disabled flags), casting (channeling, cast_delay, ability_selected, busy, parrying, ...), stamina / stamina_max, and the weapon (clip, reloading, active_reload_window, zoomed, next_attack). |
| `can` | `action.can(act: string) -> boolean` | safe | True when the action is possible now. |
| `why` | `action.why(act: string) -> string` | safe | Why the action is not possible ("None" when it is): e.g. "Dead", "Typing", "Stunned", "Zipline", "Channel", "Cooldown", "NoStamina", "NoAbility", "Reloading". |
| `decide` | `action.decide(role: string, act: string) -> string, string` | safe | The automation gate for a feature of that role: "act" \| "hold" \| "cancel", and the reason. A script that presses for the player should only press on "act". |
| `button` | `action.button(act: string) -> integer` | safe | The IN_* bit the game listens to for the action (0 for "move" / "look"). |

### trigger

`table` · tier `safe` — The triggerbot ("Shoot It For Me" on the Target Matrix class rows) as scripts see it, read-only: the state its one producer publishes each tick. Nothing here shoots or changes a setting. kind: "heroes", "troopers", "neutrals", "souls", "objectives", "deployables".

| Member | Signature | Tier | Description |
|---|---|---|---|
| `state` | `trigger.state() -> table` | safe | A fresh table: active (a target is picked), kind and class (its kind and Target Matrix class slug, "" when none), target (its entity index, nil when none), due_in_ms (until the shot may go, 0 once due; nil while nothing is scheduled or a crosshair shot waits for the crosshair), why ("shooting", "waiting", "aiming", "crosshair", "head_cap", "no_target", "user_firing", "off", or the action gate's reason such as "Reloading"), enabled (the kinds whose rows have it on, an array) and shots (shots started this session). |
| `kinds` | `trigger.kinds() -> string[]` | safe | The six kind names, in that order. |

### Backtrack

`namespace` · tier `safe` — Lag-compensation backtrack (PSilent): ask what past tick/position a target would be rewound to. Read-only — PSilent alone applies the rewind.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `best` | `Backtrack.best(target: PlayerPawn) -> table\|nil` | safe | The record PSilent WOULD rewind `target` to if it fired this tick: { pos:Vector3, tick:integer, depth:integer, time:number, ms:number, visible:boolean, usable:boolean, angles:{pitch,yaw,roll} }. nil when Backtrack is off, `target` is not a player pawn, or no visible in-window sample exists — never a stale or out-of-window record. Game thread only. |
| `at` | `Backtrack.at(target: PlayerPawn, tick: integer) -> table\|nil` | safe | The record at EXACTLY `tick`, same shape as Backtrack.best. A near-miss is never substituted: nil means there is no acceptable record at that tick. Game thread only. |
| `records` | `Backtrack.records(target: PlayerPawn) -> table\|nil` | safe | Every stored sample for `target`, oldest -> newest, each in the Backtrack.best shape. Introspection/debug: unlike best/at this is NOT gated on the enabled toggle, so test each record's `usable` (visible AND inside the rewind window) before trusting it. Game thread only. |
| `active` | `Backtrack.active() -> Vector3\|nil` | safe | The historical point PSilent actually COMMITTED this tick (nil on a tick that did not backtrack). The one Backtrack call that is render-safe — usable from on_paint to draw the rewind point. |
| `window` | `Backtrack.window() -> table\|nil` | safe | The live rewind limits: { enabled:boolean, now_tick:integer, tickrate:number, depth:integer, ms:number, max_depth:integer, max_ms:number }. depth/ms = what the slider asks for (already clamped); max_depth/max_ms = the hard sv_maxunlag ceiling. nil when there is no tick timeline. |
| `tick_valid` | `Backtrack.tick_valid(tick: integer) -> boolean` | safe | Would the server accept a rewind to `tick` right now? A pure window test — it does not say whether any target has a sample at that tick (ask Backtrack.at for that). |
| `enabled` | `Backtrack.enabled() -> boolean` | safe | Is the Backtrack feature on? While it is off PSilent rewinds nothing, and best/at return nil. |

### log

`namespace` · tier `safe` — Structured logging (debug/info/warn/error).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `debug` | `log.debug(...: any) -> nil` | safe | Variadic, space-joined; text is data, never a format string. Shows in the in-menu console (debug tint). |
| `info` | `log.info(...: any) -> nil` | safe | Variadic, space-joined. Shows in the single in-menu console stream. |
| `warn` | `log.warn(...: any) -> nil` | safe | Variadic, space-joined. Shows in the in-menu console (warn color). |
| `error` | `log.error(...: any) -> nil` | safe | Variadic, space-joined. Shows in the console (error color) AND is appended to lua_errors.log on disk (dated, bounded) for sending to the dev. |
| `to_file` | `log.to_file(enabled: boolean) -> boolean` | safe | Toggle the per-level DevLog file sink (separate from the always-on error log). |

### lua_convar_t

`usertype` · tier `safe` — Read-only Source2 ConVar value handle (convar.<name>).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `float` | `:float() -> number` | safe |  |
| `int` | `:int() -> integer` | safe |  |
| `bool` | `:bool() -> boolean` | safe |  |
| `string` | `:string() -> string` | safe | The value as text: a string convar's value (at most 1023 bytes), a number as text (integers and bools as an integer, floats with %g); "" for other kinds (colors, vectors) or an invalid convar. |
| `get_string` | `:get_string() -> string` | safe | The value as text: a string convar's value (at most 1023 bytes), a number as text (integers and bools as an integer, floats with %g); "" for other kinds (colors, vectors) or an invalid convar. |
| `get_address` | `:get_address() -> integer\|nil` | safe | The ConVar's address; nil without the "schema.raw_read" capability (trusted scripts only). |

### lua_target_selection_wrapper_t

`usertype` · tier `safe` — Self-contained filter+scoring target selector.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set_filter` | `:set_filter(predicate: fun(entity:PlayerPawn):boolean) -> nil` | safe |  |
| `add_criterion` | `:add_criterion(scorer: fun(entity:PlayerPawn):number, weight: number) -> nil` | safe |  |
| `set_flag` | `:set_flag(value: boolean) -> nil` | safe |  |
| `set_int` | `:set_int(value: integer) -> nil` | safe |  |
| `set_scalar` | `:set_scalar(value: number) -> nil` | safe |  |
| `set_mode` | `:set_mode(mode: string) -> nil` | safe |  |
| `set_target` | `:set_target(target: PlayerPawn) -> nil` | safe |  |
| `configure` | `:configure(cfg: table) -> nil` | safe |  |
| `get_config` | `:get_config() -> table` | safe |  |
| `run` | `:run() -> PlayerPawn\|nil` | safe |  |
| `reset` | `:reset() -> nil` | safe |  |

### Particle

`namespace` · tier `safe` — Particle-effect spawning (cache/place/attach/activate).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `create` | `Particle.create(name: string) -> ParticleHandle\|nil` | safe | Cache the named effect (no CP/activate); chain :at/:attach/:forward/:orientation then :activate(). |
| `spawn` | `Particle.spawn(name: string, pos: Vector3) -> ParticleHandle\|nil` | safe | One-shot: cache + place CP0 at pos + activate. |
| `attach_type` | `.attach_type: table` | safe | PATTACH_* constants for :attach (ABSORIGIN, ABSORIGIN_FOLLOW, POINT_FOLLOW, EYES_FOLLOW, OVERHEAD_FOLLOW, CENTER_FOLLOW, WORLDORIGIN, ...). |

### particle

`table` · tier `safe` — Engine particle helpers keyed by the on_particle_* events' particle index.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `control_point` | `particle.control_point(index: integer, cp: integer) -> Vector3\|nil` | safe | Any effect in the game by its particle index (the on_particle_* events' field, not a handle Create returned): the last position written to control point cp (0-7) since its create; nil when the effect is not alive or nothing wrote that point. Any thread. |

### ParticleHandle

`usertype` · tier `safe` — Chainable particle-effect handle returned by Particle.create / Particle.spawn.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `at` | `:at(cp: integer, v: Vector3) -> ParticleHandle` | safe |  |
| `attach` | `:attach(cp: integer, ent: any, attach_type?: integer, attach_point?: string) -> ParticleHandle` | safe |  |
| `forward` | `:forward(cp: integer, dir: Vector3) -> ParticleHandle` | safe |  |
| `orientation` | `:orientation(cp: integer, ang: Vector3) -> ParticleHandle` | safe |  |
| `activate` | `:activate() -> ParticleHandle` | safe |  |
| `stop` | `:stop(hard?: boolean, play_end_cap?: boolean)` | safe |  |
| `valid` | `:valid() -> boolean` | safe |  |
| `index` | `:index() -> integer` | safe |  |

### http

`namespace` · tier `safe` — Async HTTP(S) client (worker thread; callback on the game thread). UNTRUSTED/marketplace scripts limited to a host allowlist; TRUSTED bundle scripts unrestricted.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `request` | `http.request(url: string) -> HttpRequest` | safe | Build a request; chain then :send(cb). Allowlist-gated for untrusted scripts. |
| `get` | `http.get(url: string, cb?: fun(resp:table)) -> nil` | safe | Async GET; resp={status,ok,headers,body,json?,error?}. Allowlist-gated for untrusted. |
| `post` | `http.post(url: string, body: string, cb?: fun(resp:table)) -> nil` | safe | Async POST (Content-Type: application/json). Allowlist-gated for untrusted. |
| `put` | `http.put(url: string, body: string, cb?: fun(resp:table), headers?: table) -> table` | safe | Async PUT. Returns a pending stub {ok=false,pending=true,id=<cancel handle>}; the real response goes to cb on the game thread. |
| `delete` | `http.delete(url: string, cb?: fun(resp:table), headers?: table) -> table` | safe | Async DELETE. Same pending-stub return as http.put. |
| `head` | `http.head(url: string, cb?: fun(resp:table), headers?: table) -> table` | safe | Async HEAD. Same pending-stub return as http.put. |
| `options` | `http.options(url: string, cb?: fun(resp:table), headers?: table) -> table` | safe | Async OPTIONS. Same pending-stub return as http.put. |

### HttpRequest

`usertype` · tier `safe` — Fluent HTTP request builder from http.request(url); chain :method/:header/:body/:accept_json/:timeout then :send(cb).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `method` | `:method(method: string) -> HttpRequest` | safe | Set HTTP method (GET/POST/PUT/PATCH/...). |
| `header` | `:header(key: string, value: string) -> HttpRequest` | safe | Add a request header. |
| `body` | `:body(body: string) -> HttpRequest` | safe | Set the request body. |
| `accept_json` | `:accept_json() -> HttpRequest` | safe | Send Accept: application/json and parse resp.json. |
| `timeout` | `:timeout(ms: integer) -> HttpRequest` | safe | Per-request timeout in ms (clamped 250..120000). |
| `send` | `:send(cb?: fun(resp:table)) -> nil` | safe | Dispatch on a worker thread; cb runs on the game thread with the response table. |

### net_channel

`namespace` · tier `safe` — Network channel timing (tick/interval/time, real live-verified latency).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `latency` | `.latency: number` | safe | Live CNetChan round-trip latency in SECONDS, resolved on read via an __index metatable (agrees with get_latency(); channel 0). 0.0 when disconnected. (Was a dead static 0.0 snapshot before — now genuinely live.) |
| `get_latency` | `net_channel.get_latency(nChannel?: integer) -> number` | safe | Live CNetChan round-trip latency in SECONDS (real, live-verified vtable read - NOT a stub). nChannel defaults to 0 (the populated client channel); returns 0.0 when disconnected. |
| `packet_loss` | `net_channel.packet_loss(flow?: integer) -> number` | safe | Live CNetChan average packet LOSS as a fraction 0..1 (x100 for %). Same CNetChan as get_latency (vtable[12] GetAvgLoss). flow defaults to 1 = INCOMING (server->client); pass 0 for OUTGOING. 0.0 when disconnected. |
| `choke` | `net_channel.choke(flow?: integer) -> number` | safe | Live CNetChan average CHOKE as a fraction 0..1 (x100 for %). Same CNetChan as get_latency (vtable[13] GetAvgChoke). flow defaults to 1 = INCOMING; pass 0 for OUTGOING. 0.0 when disconnected. |
| `avg_data` | `net_channel.avg_data(flow?: integer) -> number` | safe | Live CNetChan average throughput in BYTES/sec for the flow (vtable[15] GetAvgData). flow defaults to 1 = INCOMING. 0.0 when disconnected. |
| `avg_packets` | `net_channel.avg_packets(flow?: integer) -> number` | safe | Live CNetChan average PACKETS/sec for the flow (vtable[16] GetAvgPackets). flow defaults to 1 = INCOMING. 0.0 when disconnected. |
| `get_tick` | `net_channel.get_tick() -> integer` | safe | Current sim tick count (CGlobalVarsBase::m_nTickCount). |
| `get_server_tick` | `net_channel.get_server_tick() -> integer` | safe | Server tick - mirrors the sim tick on this build (no distinct client/server tick source is exposed). |
| `get_interval_per_tick` | `net_channel.get_interval_per_tick() -> number` | safe | Seconds per tick (m_flIntervalPerTick; 1/64 fallback). |
| `get_curtime` | `net_channel.get_curtime() -> number` | safe | Current game time in seconds (m_flCurrentTimeRaw). |
| `get_realtime` | `net_channel.get_realtime() -> number` | safe | Real (wall-clock) time in seconds (m_flRealTime). |
| `get_frametime` | `net_channel.get_frametime() -> number` | safe | Absolute frame time in seconds (m_flAbsoluteFrameTime). |
| `ticks_to_time` | `net_channel.ticks_to_time(ticks: number) -> number` | safe | Convert ticks -> seconds (ticks * interval_per_tick). |
| `time_to_ticks` | `net_channel.time_to_ticks(seconds: number) -> integer` | safe | Convert seconds -> ticks (rounded). |
| `is_valid` | `net_channel.is_valid() -> boolean` | safe | True when the global-vars source is available. |
| `send_net_message` | `net_channel.send_net_message(name: string, fields?: table\|string) -> boolean\|nil, string?` | safe | Sends the client net message `name` (its protobuf type, e.g. "CCitadelClientMsg_ExecuteMapPositionAbility") to the server on the local player's channel. fields is a table or a JSON object keyed by the message's field names, checked against the type before anything is allocated; nil sends the defaults. Game thread. true, or nil and the reason. |

### net

`namespace` · tier `safe` — Generic inbound protobuf message read (reflection-based).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_message` | `net.on_message(name_or_id: string\|integer, callback: fun(msg:table)) -> integer` | safe | Register an observer for inbound user-messages. matcher = descriptor name/full_name, a numeric msg id, or "*" for all. callback(msg) receives the decoded protobuf fields as a table (+ .name / .id); its return value is IGNORED (never swallows the message). Returns a handle. |
| `remove_message` | `net.remove_message(handle: integer) -> boolean` | safe | Remove a handler registered via net.on_message (true if found). |

### proto

`namespace` · tier `safe` — Bidirectional protobuf: parse raw bytes into a table, or serialize a table into bytes, by message type name.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `parse` | `proto.parse(type_name: string, bytes: string) -> table\|nil` | safe | Decode raw wire bytes of message `type_name` into a Lua table of its fields via reflection (nested messages depth-capped, repeated -> 1-based arrays). Returns nil + logs on unknown type / parse failure. |
| `serialize` | `proto.serialize(type_name: string, tbl: table) -> string\|nil` | safe | Build a fresh `type_name` message from `tbl` via reflection setters, then serialize to raw bytes (a Lua string). Unknown keys / type mismatches are logged + skipped; returns nil + logs on unknown type / serialize failure. |
| `has_type` | `proto.has_type(type_name: string) -> boolean` | safe | True if `type_name` is a message type known to the generated descriptor pool. |
| `list_types` | `proto.list_types() -> table` | safe | Array of known message full-names (dependency closure of the core network message files; deduped, sorted, capped) for discoverability. |

### common

`namespace` · tier `safe` — General helpers (identity, RNG, timing, easing, bit ops).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_username` | `common.get_username() -> string` | safe | Host USERNAME env var ("unknown" if unset). |
| `get_game_directory` | `common.get_game_directory() -> string` | safe | Directory of the host process's main module. |
| `get_server_info` | `common.get_server_info() -> table` | safe | Snapshot of server/match info: map_name, map_group, max_players, player_count, tick_interval, tick_count, frame_count, current_time, is_in_game, match_time (+game_state/game_mode/match_mode/spectator_count/paused when GameRules is live). game_state is the raw EGameState (0..11): 7 = GameInProgress, 8 = PostGame. |
| `random_int` | `common.random_int(min: integer, max: integer) -> integer` | safe | Uniform integer in [min, max]. |
| `random_float` | `common.random_float(min: number, max: number) -> number` | safe | Uniform float in [min, max]. |
| `random_string` | `common.random_string(length: integer, charset?: string) -> string` | safe | Random string (default alphanumeric charset). |
| `execute_after` | `common.execute_after(delay: number, fn: function) -> integer\|nil` | safe | Fire fn once on the game thread after delay seconds (forwards to set_timeout). |
| `mark` | `common.mark(key: string)` | safe | Stamp key with the current game time. |
| `time_since` | `common.time_since(key: string) -> number` | safe | Seconds since key was last marked (huge if never). |
| `throttle` | `common.throttle(key: string, seconds: number) -> boolean` | safe | True (and re-stamps) once seconds elapse since the last success. |
| `crash_note` | `common.crash_note(tag: string, what: string, a: number?, b: number?)` | safe | Write a line to crash.log that SURVIVES a hard kill (flushed per line). Use to find where a script hangs: mark each phase, and the last line in the log names the phase that never finished. Costs a file write per call -- do not leave in hot paths. |
| `reset_timer` | `common.reset_timer(key: string)` | safe | Forget key's mark. |
| `band` | `common.band(a: integer, b: integer) -> integer` | safe | Bitwise AND. |
| `bor` | `common.bor(a: integer, b: integer) -> integer` | safe | Bitwise OR. |
| `bxor` | `common.bxor(a: integer, b: integer) -> integer` | safe | Bitwise XOR. |
| `bit_set` | `common.bit_set(mask: integer, flag: integer) -> boolean` | safe | True if every bit of flag is set in mask. |
| `bit_test` | `common.bit_test(mask: integer, bit: integer) -> boolean` | safe | True if bit index (0..30) is set in mask. |
| `ease_in` | `common.ease_in(t: number) -> number` | safe | Cubic ease-in (t clamped 0..1). |
| `ease_out` | `common.ease_out(t: number) -> number` | safe | Cubic ease-out (t clamped 0..1). |
| `ease_in_out` | `common.ease_in_out(t: number) -> number` | safe | Cubic ease-in-out (t clamped 0..1). |
| `smoothstep` | `common.smoothstep(t: number) -> number` | safe | Hermite smoothstep (t clamped 0..1). |
| `lerp_angle` | `common.lerp_angle(a: number, b: number, t: number) -> number` | safe | Angular lerp taking the shortest path. |
| `vtos` | `common.vtos(v: Vector3) -> string` | safe | Format a Vector3 as "(x, y, z)". |

### anim

`namespace` · tier `safe` — Native animation / easing helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ease_in` | `anim.ease_in(t: number) -> number` | safe |  |
| `ease_out` | `anim.ease_out(t: number) -> number` | safe |  |
| `ease_in_out` | `anim.ease_in_out(t: number) -> number` | safe |  |
| `smoothstep` | `anim.smoothstep(t: number) -> number` | safe |  |
| `lerp` | `anim.lerp(a: number, b: number, t: number) -> number` | safe |  |
| `lerp_angle` | `anim.lerp_angle(a: number, b: number, t: number) -> number` | safe |  |
| `value` | `anim.value(key: string, target: number, speed: number) -> number` | safe | Per-key eased scalar approaching target at speed/sec (game-time stepped). |
| `fade` | `anim.fade(key: string, on: boolean, speed: number, max_alpha?: number) -> number` | safe | Eased 0->max_alpha (on) / ->0 (off); max_alpha defaults 255. |
| `reset` | `anim.reset(key: string)` | safe | Forget a key's eased-value state. |

### color

`namespace` · tier `safe` — Color construction / conversion helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `rgb` | `color.rgb(r: integer, g: integer, b: integer, a?: integer) -> Color` | safe | Construct a Color from 0..255 components (a defaults 255). |
| `from_hex` | `color.from_hex(hex: string) -> Color` | safe | Parse "#RRGGBB" / "#RRGGBBAA" (leading # optional). |
| `lerp` | `color.lerp(a: Color, b: Color, t: number) -> Color` | safe | Component-wise lerp a->b (t clamped 0..1). |
| `from_hsv` | `color.from_hsv(h: number, s: number, v: number, a?: integer) -> Color` | safe | HSV (h in degrees, s/v 0..1) -> Color. |
| `rainbow` | `color.rainbow(t: number, a?: integer) -> Color` | safe | Cycle hue by t (wraps at 1.0) -> fully-saturated Color. |

### config_state

`namespace` · tier `safe` — Poll-based menu/config value change watcher.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `watch` | `config_state.watch(getter: fun():any, on_change: fun(new:any, old:any)) -> integer` | safe | Poll getter each tick; fire on_change when its return changes. Returns a watcher id. |
| `unwatch` | `config_state.unwatch(id: integer) -> boolean` | safe | Remove a watcher by id. |
| `count` | `config_state.count() -> integer` | safe | Number of active watchers. |

### esp

`namespace` · tier `safe` — ESP element builder root; esp.enemy attaches custom text/bars to the native enemy ESP overlay.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `enemy` | `.enemy: table` | safe | Per-enemy ESP element builder (see esp.enemy:new_text / :new_bar). |
| `register_class` | `esp.register_class(spec: table) -> EspClass\|nil` | safe | Registers a script entity class as its own row of the Visuals Entities list. spec = { id (1-31 of a-z 0-9 _, not a built-in key), label, group ("npcs" \| "objectives" \| "deployables" \| "pickups"), art? = { hero = <codename>, slot = 1..4 }, cells? (the cells the row offers: on, color, name, icon, dist, timer, alert, team, maxdist), default? (the cells' starting values; every class starts off) }. At most 32 script classes; the set is cleared when the script unloads. nil after a console error. |
| `class` | `esp.class(name: string, opts?: table) -> EspClass\|nil` | safe | A built-in Entities class (troopers, neutrals, sacrifice, breakables, midboss, guardians, walkers, patron, shrines, talon, bebop, mcginnis, venator, graves, souls, powerups, projectiles). opts.provides = { "timer", "alert" } adds those cells to the built-in row for this script to drive. |
| `entity_display` | `esp.entity_display() -> number, number, number` | safe | The Entities display row every class shares: text size (px), icon size (px), fade (%). |

### esp.enemy

`namespace` · tier `safe` — Per-enemy ESP element builder — esp.enemy:new_text / :new_bar.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `new_text` | `:new_text(callback: fun(entity:Entity):string\|nil) -> EspElement` | safe | Add a text row below each enemy's ESP box; callback returns the string to draw (nil skips that enemy this frame). Chainable EspElement. |
| `new_bar` | `:new_bar(callback: fun(entity:Entity):number\|nil) -> EspElement` | safe | Add a fill bar below each enemy's ESP box; callback returns a 0.0-1.0 fraction (nil skips that enemy this frame). Chainable EspElement. |

### EspElement

`usertype` · tier `safe` — Chainable ESP element handle returned by esp.enemy:new_text / :new_bar.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set_color` | `:set_color(color: Color) -> EspElement` | safe | Set the element color (Color/ImColor or { r,g,b,a } table). Returns self. |
| `set_offset` | `:set_offset(x: number, y: number) -> EspElement` | safe | Pixel offset from the row anchor. Returns self. |
| `remove` | `:remove()` | safe | Unregister this element so its callback stops firing. |

### EspClass

`usertype` · tier `safe` — A script or built-in Entities class handle (esp.register_class / esp.class).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get` | `:get(cell: string) -> any` | safe | The cell's value now: on, name, icon, dist, timer, alert (booleans), team (integer), maxdist (meters), alert_lead (seconds), color (Color); nil for a cell the class does not have or a class that is gone. |

### MenuInject

`namespace` · tier `safe` — Full menu/UI injection: add widgets/tabs to native pages, inject combo options, read/override any menu value, conditionally hide/disable/annotate native options.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `page` | `MenuInject.page(id: string) -> MenuNode\|nil` | safe | Inject widgets IN PLACE at a native page's Lua anchor. id in {"aim","visuals","misc","settings"} returns that reserved root's MenuNode builder; any other id falls back to a standalone rail tab titled after the id. |
| `zone` | `MenuInject.zone(id: string) -> MenuNode\|nil` | safe | Alias of MenuInject.page (same four anchored zones). |
| `tab` | `MenuInject.tab(title: string) -> MenuNode\|nil` | safe | Create/return a first-class rail tab (new page) as a MenuNode builder — the new-page / new-tab entry point. |
| `page_new` | `MenuInject.page_new(title: string) -> MenuNode\|nil` | safe | Alias of MenuInject.tab. |
| `combo_add_option` | `MenuInject.combo_add_option(slug: string, ...: string) -> integer` | safe | Append one or more extra choices to a native combo (by SettingsStore slug) at draw time; returns the new injected-extra count. |
| `combo_clear` | `MenuInject.combo_clear(slug: string) -> boolean` | safe | Drop the injected extra choices for a native combo (true if any were present). |
| `combo_options` | `MenuInject.combo_options(slug: string) -> string[]` | safe | 1-based array of the combo's native choices followed by any injected extras. |
| `get_value` | `MenuInject.get_value(path: string) -> any` | safe | Read a slash-path ConfigStore value (Lua menu + hero-script values); nil if absent. Type inferred from the stored value. |
| `set_value` | `MenuInject.set_value(path: string, value: any) -> boolean` | safe | Write a slash-path ConfigStore value (bool/number/string/color table); type inferred from the Lua value. |
| `native_get` | `MenuInject.native_get(slug: string) -> any` | safe | Read a native fw option's value by slug (typed per its schema); nil if the slug is unknown. |
| `native_set` | `MenuInject.native_set(slug: string, value: any) -> boolean` | safe | Write a native fw option's BASE value by slug (persisted, exactly as a user edit would); false if the slug is unknown. |
| `native_options` | `MenuInject.native_options() -> table` | safe | Array of every native option: { slug=, label=, type= } for discovery/addressing. |
| `set_visible` | `MenuInject.set_visible(slug: string, cond: boolean\|fun():boolean\|nil) -> boolean` | safe | Hide a native option when cond is false or the predicate fn() returns false; nil clears. Predicate faults fail OPEN (visible). |
| `set_disabled` | `MenuInject.set_disabled(slug: string, cond: boolean\|fun():boolean\|nil) -> boolean` | safe | Grey + lock a native option when cond is true or the predicate fn() returns true; nil clears. Predicate faults fail OPEN (enabled). |
| `set_tooltip` | `MenuInject.set_tooltip(slug: string, text: string\|nil) -> boolean` | safe | Add/override a native option's hover tooltip; nil or "" clears. |
| `clear_native` | `MenuInject.clear_native(slug: string) -> boolean` | safe | Drop every override (visible/disable/tooltip) for a native option (true if any were present). |
| `style` | `MenuInject.style(name?: string) -> Color\|table` | safe | Forward to Menu.Style: themed color for a palette name, or the full theme table with no arg. |

### HeroCfg

`namespace` · tier `safe` — Read-only view of the local hero's persisted combo/aim config (the Heroes page), plus ctx-resolved script-scope option reads.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get` | `HeroCfg.get() -> table` | safe | The LOCAL hero's whole persisted combo/aim config as a READ-ONLY table (writes raise): { hero_id, version, combo_key, combo_key_mode, show_visuals, lua_override, ability_order[4], abilities[4] = { enabled, manual_enabled, aim = {...}, combo_items = {...}, manual_items = {...}, weapon_override = {...} }, targets = { combo, helpers }, standalone }. Each targets column is { fov, max_dist_m, priority, lock, visible_only, ignore_mask }; its fov is the cone radius in degrees (angle <= fov), like every aim cone, and half the number older builds gave (the full width). Cached against the config version, so re-reading it every tick is free. Empty table when there is no local hero (test cfg.hero_id). |
| `version` | `HeroCfg.version() -> integer` | safe | The config version HeroCfg.get()'s table was built from; bumps on every published config edit (cheap change detection). |
| `hero_id` | `HeroCfg.hero_id() -> integer` | safe | The local hero's raw id, or -1 when there is no local hero. |
| `native_get` | `HeroCfg.native_get(slug: string) -> any` | safe | A script-scope SettingsStore option for the local hero, resolved Hero -> Global (the per-hero override master applies). Unlike MenuInject.native_get, which reads the BASE value with no context layer. |
| `native_get_ability` | `HeroCfg.native_get_ability(slot: integer, slug: string) -> any` | safe | The same option resolved Ability -> Hero -> Global for signature-ability slot 0..3; a slot outside 0..3 degrades to HeroCfg.native_get. |
| `manual_triggered` | `HeroCfg.manual_triggered(slot: integer) -> boolean` | safe | THE manual-cast entry point for signature slot 0..3: true on the tick the PLAYER pressed that ability himself AND the Heroes page has 'Runs when you cast Ability N yourself' on for it — and, when true, SWALLOWS the raw press so the game never fires it and your script can cast it aimed instead. True exactly once per physical press (a held key does not re-trigger). The swallow carries a replay obligation: if no cast is produced within HeroCfg.manual_replay_window() seconds, the latch presses the ability itself, so a swallowed press is never silently lost. |
| `user_pressed` | `HeroCfg.user_pressed(slot: integer) -> boolean` | safe | Did the PLAYER press signature ability `slot` (0..3) himself THIS tick? A true rising edge, read from the pristine pre-injection command — unlike cmd:get_orig_button_state1(), which aliases the live, already-mutated field. Pure query: arms nothing. |
| `user_holding` | `HeroCfg.user_holding(slot: integer) -> boolean` | safe | Is the PLAYER's key for signature ability `slot` (0..3) DOWN this tick (held, not necessarily a fresh press)? Pristine; arms nothing. |
| `swallow` | `HeroCfg.swallow(slot: integer) -> boolean` | safe | Raw escape hatch: arm the swallow for signature slot 0..3 without the manual_enabled config gate. Only ever takes a press the player is actually making this tick, and never one that already produced its cast — so it can never conjure a replay for an input that was never made. true = a swallow session is open afterwards. |
| `release` | `HeroCfg.release(slot: integer) -> boolean` | safe | Hand a swallowed press back: closes the session for signature slot 0..3, and if it never produced a cast the latch presses the ability THIS tick (the replay obligation, discharged early). true = a session was open. |
| `discard` | `HeroCfg.discard(slot: integer) -> boolean` | safe | DROP a swallowed press for signature slot 0..3: closes the session with NO replay, so the ability is never cast. This is the DELIBERATE-REFUSAL counterpart to release() — use it when your own gates said no (a ticked 'Require Target' with nothing targetable, out of range, a hero rule), because replaying there would fire the exact ability the user's configuration just declined. The latch still clears every carrier on the way out, so the raw press cannot leak. Use release() for a FAILURE (stall/timeout/cancel), where the player is still owed the press. true = a session was open. |
| `manual_keepalive` | `HeroCfg.manual_keepalive(slot: integer) -> boolean` | safe | Tell the latch your manual timeline is STILL WORKING this press: restarts the replay window for signature slot 0..3. Without it the window measures from the PRESS, so any manual run that legitimately takes longer than manual_replay_window() (acquiring a target, parked on a gate, casting a chained item, serving a cast-settle) gets the player's RAW press fired out from under it — an unaimed cast, then your real aimed one. Call it every tick a manual run is alive. The press is still never lost: your watchdog reaps a wedged run into release(), and a script that dies stops heartbeating so the window fires anyway. true = a session was open. |
| `manual_replays` | `HeroCfg.manual_replays() -> integer` | safe | How many swallowed presses the replay safety net has had to fire (cumulative). A rising count means a script is arming the swallow and not casting — the fallback is working, but the script is not. |
| `manual_replay_window` | `HeroCfg.manual_replay_window(seconds?: number) -> number` | safe | The swallow's replay deadline in seconds (default 0.25, clamped 0..1): how long a script has to produce its cast before the latch presses the ability itself. Returns the current value; pass a number to set it. |
| `enums` | `HeroCfg.enums() -> table` | safe | The native enums behind HeroCfg.get()'s values, by the names the bundled scripts use, plus ITEM (EComboItem). A fresh plain table per call: read it once at load. |
| `item_tokens` | `HeroCfg.item_tokens() -> table` | safe | { [EComboItem index] = vdata record token } for the combo item list. |
| `key_vk` | `HeroCfg.key_vk(stored_key: integer) -> integer` | safe | A stored bind key (ImGuiKey numbering, or a VK below 256) as a Windows VK, 0 for none: the rule the bind evaluator uses. |
| `key_down` | `HeroCfg.key_down(stored_key: integer) -> boolean` | safe | The stored bind key is held in the game (Input.is_key_down's rule). |

### ComboOpt

`namespace` · tier `safe` — Declare your own option rows on the native Heroes page (per ability / per combo item / per always-on FEATURE) and read them back. Owner + hero are auto-filled.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ability` | `ComboOpt.ability(slot: integer, hero?: integer) -> ComboOptScope` | safe | A declaration scope on signature ability `slot` (0..3) of the LOCAL hero — the rows appear in that ability's Aim & Targeting child. Pass `hero` to target a specific hero id, or 0 to show the rows on EVERY hero. |
| `item` | `ComboOpt.item(item: integer\|string, hero?: integer) -> ComboOptScope` | safe | A declaration scope on a combo ITEM — its EComboItem ordinal or its "upgrade_*" vdata token ("upgrade_metal_skin"). The rows appear in that item's combo card. Pass `hero` to target a specific hero id, or 0 for every hero. |
| `get` | `ComboOpt.get(key: string) -> any` | safe | The live value of one of THIS script's declared options (nil if it never declared `key`). Bool -> boolean, slider -> number, slider_int -> integer, enum -> the 1-based index into `choices`. Cheap enough to call every tick (cached handle + atomic read, no menu lock). ComboOpt.get(owner, key) reads another script's option. |
| `feature` | `ComboOpt.feature(spec: table)` | safe | Declare an always-on FEATURE: an enabled toggle (+ optional bind) plus 0..N sub-option rows. spec = { key, label, blurb?, default?, bind?, hero?, slot?, options={ { type="toggle"\|"slider"\|"slider_int"\|"dropdown"\|"color"\|"header"\|"hint", key, label?, tooltip?, default?, min?, max?, step?, fmt?, choices?, bind?, depends_on?, depends_value?, depends_not? }, ... } }. Read back with feature.enabled / feature.value. A bare `slider` with an integer `step` rounds (Int); otherwise it is a Float. `depends_on` names a sibling option key; `depends_not=true` inverts the depends_value test (show when the sibling != depends_value). Optional `slot` (0..3) binds the feature to an ability so the per-ability panel cross-links to it. Option type "multi" takes choices (at most 24) and a default list / set / mask. `depends = { { on, value, negate }, ... }` lists more conditions, all of which must hold. Feature flags: casts (the feature fires its slot's ability; its helper row reads "Auto: <Ability>"), indicator (a slotless read-out the hero page seats on its Kill Indicator row). |

### ComboOptScope

`usertype` · tier `safe` — Chainable declaration handle returned by ComboOpt.ability / ComboOpt.item — :toggle / :slider / :slider_int / :enum / :color / :header / :hint.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `toggle` | `:toggle(spec: table) -> ComboOptScope` | safe | Declare a toggle row: { key="storm_hud", label="Storm Counter HUD", tooltip=?, default=false }. `key` is required and must be unique within the script (ComboOpt.get addresses it). Returns self. |
| `slider` | `:slider(spec: table) -> ComboOptScope` | safe | Declare a float slider row: { key="lead", label="Lead", min=0, max=1, default=min, fmt="%.2f", tooltip=? }. Returns self. |
| `slider_int` | `:slider_int(spec: table) -> ComboOptScope` | safe | Declare an integer slider row: { key="stacks", label="Stacks", min=0, max=10, default=min, fmt="%d", tooltip=? }. Returns self. |
| `enum` | `:enum(spec: table) -> ComboOptScope` | safe | Declare a dropdown row: { key="style", label="Style", choices={"A","B"}, default=1 }. `default` and the value ComboOpt.get returns are both the 1-BASED index into `choices`. Returns self. |
| `color` | `:color(spec: table) -> ComboOptScope` | safe | Declare a color row: { key="tint", label="Tint", default=0x2EE6D6FF }. `default` and ComboOpt.get are the 32-bit RGBA integer. Returns self. |
| `header` | `:header(spec: table) -> ComboOptScope` | safe | Declare a caps section-divider row (no value): { label="TARGETING" }. `key` optional. Returns self. |
| `hint` | `:hint(spec: table) -> ComboOptScope` | safe | Declare a static dim helper-text row (no value): { label="needs a target in FOV" }. `key` optional. Returns self. |
| `multi` | `:multi(spec: table) -> ComboOptScope` | safe | A multi-select row: spec = { key, label, choices (at most 24), default (a list of 1-based indices, a set or a bitmask) }; read back as a set { [index] = true }. |

### feature

`namespace` · tier `safe` — Read back an always-on FEATURE (declared via ComboOpt.feature): feature.enabled(key) and feature.value(key, opt). Owner + local hero auto-filled.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `enabled` | `feature.enabled(key: string, owner?: string) -> boolean` | safe | The enabled state of an always-on feature (false if it was never declared). Cheap every-tick read (cached handle + atomic). |
| `value` | `feature.value(key: string, opt: string, owner?: string) -> any` | safe | The live value of a feature sub-option, typed by kind: toggle->boolean, slider->number, slider_int->integer, dropdown->1-based index, color->32-bit RGBA integer, multi->read-only set { [choice index] = true } (the same table while the value is unchanged). nil if never declared. Reads the scoped hero's row under feature.scope. |
| `color` | `feature.color(key: string, opt: string, owner?: string) -> integer, integer, integer, integer` | safe | A `color` sub-option decomposed into r, g, b, a (0..255) — splat straight into Color(...). Opaque white when unresolved. |
| `scope` | `feature.scope(hero_id?: integer) -> integer\|nil` | safe | Until reset with nil (or 0), this script's feature.enabled / value / color read the rows filed under that hero instead of the local hero's (stolen ultimates). Returns the previous scoped hero or nil. Every callback starts unscoped. |

### Panorama

`namespace` · tier `safe` — Panorama UI control (run JS / find/create/restyle HUD panels). Open to ALL scripts: JS runs in the game's Panorama UI layer, not raw process memory / native code, so it is Safe-tier (not gated like mem/hooks/native/ffi).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `available` | `Panorama.available() -> boolean` | safe | True if a Panorama call would run right now (game thread, not mid-map-change, engine+HUD panel up). |
| `run_script` | `Panorama.run_script(js: string, panel?: PanoramaPanel) -> boolean` | safe | Run Panorama JS in the HUD context (or bound to self=panel). false = it didn't run. |
| `run_js` | `Panorama.run_js(js: string, panel?: PanoramaPanel) -> boolean` | safe | Alias of run_script. |
| `root` | `Panorama.root() -> PanoramaPanel` | safe | Handle to the HUD root panel. |
| `context` | `Panorama.context() -> PanoramaPanel` | safe | Handle to $.GetContextPanel(). |
| `find` | `Panorama.find(id: string) -> PanoramaPanel` | safe | root.FindChildTraverse(id) handle (re-resolved each call). |
| `create` | `Panorama.create(type: string, parent?: PanoramaPanel, id?: string) -> PanoramaPanel` | safe | Create a panel of `type` under parent (default root), dedup'd by id; an omitted id gets a generated one. |

### PanoramaPanel

`usertype` · tier `safe` — Handle to a Panorama panel (JS selector).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `find_child` | `:find_child(id: string) -> PanoramaPanel` | safe | Child selector off this handle (FindChildTraverse). |
| `set_text` | `:set_text(text: string) -> PanoramaPanel` | safe | Set panel .text (Label). |
| `set_style` | `:set_style(prop: string\|table, value?: string) -> PanoramaPanel` | safe | Set one style prop, or many via { prop = value }. |
| `add_class` | `:add_class(name: string) -> PanoramaPanel` | safe | AddClass(name). |
| `remove_class` | `:remove_class(name: string) -> PanoramaPanel` | safe | RemoveClass(name). |
| `set_visible` | `:set_visible(visible: boolean) -> PanoramaPanel` | safe | visibility (collapses out of layout when false). |
| `set_attribute` | `:set_attribute(name: string, value: string) -> PanoramaPanel` | safe |  |
| `run_script` | `:run_script(js: string) -> PanoramaPanel` | safe | Run JS with local self bound to this panel. |
| `remove` | `:remove() -> PanoramaPanel` | safe | DeleteAsync(0) (deferred destroy). |
| `delete` | `:delete() -> PanoramaPanel` | safe | Alias of remove. |
| `id` | `:id() -> string` | safe | The id this handle was built from (no readback). |
| `valid` | `:valid() -> boolean` | safe | STRUCTURAL validity only (selector non-empty); NOT a live-existence check. |
| `has_selector` | `:has_selector() -> boolean` | safe | Same STRUCTURAL check as valid() under an honest name (selector non-empty); NOT a live-existence check. |
| `get_attribute` | `:get_attribute(name: string) -> nil` | safe | Not implemented: raises an error (the Panorama bridge has no JS-to-Lua return channel). |
| `children` | `:children() -> table` | safe | Not implemented: raises an error (the Panorama bridge has no JS-to-Lua return channel). |

### native

`namespace` · tier `privileged` — Native-access entry points (interfaces, vfuncs, pattern scans, netvar offsets), all disabled by policy: each returns nil and the reason. TRUSTED/local only — stripped for untrusted scripts.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `create_interface` | `native.create_interface(module_name: string, version: string) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `get_vfunc` | `native.get_vfunc(instance: integer, index: integer) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `call_vfunc` | `native.call_vfunc(instance: integer, index: integer, ret_type: string, arg_types: string[], ...: any) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `find_pattern` | `native.find_pattern(module_name: string, pattern: string, offset?: integer) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `find_pattern_range` | `native.find_pattern_range(pattern: string, start_addr: integer, end_addr: integer, offset?: integer) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `get_netvar_offset` | `native.get_netvar_offset(class_name: string, field_name: string) -> nil, string` | privileged | Disabled by policy: returns nil and a reason that points to schema.field_offset(class, field) (nil alone without the native capability). |
| `get_call_target` | `native.get_call_target(address: integer) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `get_ptr_address` | `native.get_ptr_address(address: integer, disp_offset?: integer, instr_len?: integer) -> nil, string` | privileged | Disabled by policy: returns nil and the reason (nil alone without the native capability). |
| `module_base` | `native.module_base(module_name: string) -> nil, string` | privileged | Disabled by policy: returns nil and a reason that points to memory.get_module_base(name) (nil alone without the native capability). |

### ffi

`namespace` · tier `privileged` — Curated typed-call FFI bridge (bounded scalar types, allowlisted modules; NOT real ffi.cdef parsing). TRUSTED/local only — stripped for untrusted scripts.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `load` | `ffi.load(module_name: string) -> FFILib\|nil` | privileged | Resolve an ALREADY-LOADED, allowlisted module handle (never loads a new DLL). |
| `func` | `ffi.func(addr: integer, ret_type: string, arg_types: string[]) -> FFICallable\|nil` | privileged | Build a typed callable over a raw address. |
| `cast` | `ffi.cast(type: string, address: integer) -> FFIScalar\|nil` | privileged | Typed read/write VIEW into EXISTING memory (scalar types only). |
| `new` | `ffi.new(type: string) -> userdata\|nil` | privileged | A fresh zeroed scalar of the type, owned by Lua: a userdata with :get(), :set(value) and :addr() (its address while the userdata lives), freed when it is collected. |

### FFILib

`usertype` · tier `privileged` — Handle to an allowlisted loaded module from ffi.load.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `func` | `:func(export_name: string, ret_type: string, arg_types: string[]) -> FFICallable\|nil` | privileged | Resolve export_name off this lib's module, then build a typed callable. |

### FFICallable

`usertype` · tier `privileged` — Typed callable native function pointer; invoke via ().

| Member | Signature | Tier | Description |
|---|---|---|---|
| `__call` | `:__call(...: any) -> any` | privileged | Invoke via callable(...); same SpoofCall path as mem.call/native.call_vfunc. |

### FFIScalar

`usertype` · tier `privileged` — A scalar C value view (cast) or allocation (new).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get` | `:get() -> any` | privileged | Typed read per the scalar kind (int/int64/uint/ptr/bool/float32/float64); nil on a bad address. |
| `set` | `:set(value: any) -> boolean` | privileged | Typed write; false for float32/float64 (read-only) or a bad address. |
| `addr` | `:addr() -> integer` | privileged | The underlying address. |

### HERO_LIB

`table` · tier `safe` — Native hero-script helper library (the #1 referenced global in hero scripts).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `lp` | `lp` | safe | Local pawn accessor. |
| `is_lp_valid` | `HERO_LIB.is_lp_valid() -> boolean` | safe |  |
| `is_lp_alive` | `HERO_LIB.is_lp_alive() -> boolean` | safe |  |
| `get_health` | `HERO_LIB.get_health() -> integer` | safe |  |
| `get_health_percent` | `HERO_LIB.get_health_percent() -> number` | safe |  |
| `units_to_meters` | `HERO_LIB.units_to_meters(units: number) -> number` | safe |  |
| `game_time` | `HERO_LIB.game_time() -> number` | safe |  |
| `is_ability_ready` | `HERO_LIB.is_ability_ready(ability: Ability\|integer, count_cast_delay?: boolean, accepted_codes?: table) -> boolean, boolean` | safe | Validated readiness: ready, casting. ability is an Ability, the light userdata HERO_LIB.get_ability returns, or a slot number. On the game thread inside the tick it asks the game (the action record's answer for an ability an action presses, one memoised activation check per ability per tick otherwise): Success is ready, PositionInvalid and CantCastPassive count as ready off cooldown, and so does any code in accepted_codes (each an ECitadelAbilityOrders name or number). Elsewhere the hand rules answer. count_cast_delay = true also accepts an ability inside its own cast delay, and then the second result `casting` is true. CHANGED: second result and accepted_codes are new; the game's answer is used on the game thread. |
| `is_ability_in_cd` | `HERO_LIB.is_ability_in_cd(ability: Ability\|integer, force_chargeable?: boolean) -> boolean` | safe | Cooling down, or no charge left on a chargeable ability. Accepts an Ability, light userdata or a slot number. force_chargeable: nil lets the ability's AbilityCharges decide, true treats it as chargeable, false as not. |
| `is_ability_in_cast_delay` | `HERO_LIB.is_ability_in_cast_delay(ability: Ability\|integer, no_start_offset?: boolean, delay?: number, start?: number) -> boolean` | safe | TIME-WINDOW test (NOT the m_bInCastDelay bool), Umbrella's window: start <= now + 1 s and now <= start + delay, so a start stamp up to 1 s ahead of the clock (the client's predicted press) counts. no_start_offset = true drops that 1 s lead. Optional delay / start override AbilityCastDelay and m_flCastDelayStartTime, so a caller that already read the pair skips the property resolve. False for a null ability, one authoring no cast delay, one never cast. For the raw schema flag use ability_in_cast_delay. CHANGED: arg 2 was an unread filler and the window had no lead. |
| `is_ability_in_self_cast_delay` | `HERO_LIB.is_ability_in_self_cast_delay(ability: Ability\|integer) -> boolean` | safe | The local hero's alternate-cast (self-cast) window is open for the ability: game time < the alt-cast hold start + cl_citadel_ability_alt_cast_hold_time, or the double-tap start + the double-tap timeout, by the player's alt-cast mode; false in the modifier-key mode. CHANGED: it was an alias of is_ability_in_cast_delay (same signature). |
| `get_scaled_property` | `HERO_LIB.get_scaled_property(ability: Ability, key: string) -> number` | safe | Caster-scaled property value (spirit power, item bonuses). Game thread only; an off-thread call returns the authored base value. Range and length keys come back in UNITS. Same as Ability:get_scaled_property. |
| `dump_ability` | `HERO_LIB.dump_ability(ability: Ability)` | safe | GROUND-TRUTH AUDIT AID. Appends this ability/item class's REAL authored property set (every VData-enumerated key + its scaled value) to C:\Avalanche\Config\ability_properties_dump.txt, one section per class. Deduped by class name in C++, so repeat/per-tick calls are a cheap early return (no per-tick I/O). Game-thread only. Use to discover exact property names for readers. |
| `get_cast_range` | `HERO_LIB.get_cast_range(ability: Ability) -> number` | safe | Scaled cast range in UNITS, including cast-range items (Greater Expansion etc.); 4000 when the ability declares none. Same producer as Ability:get_cast_range and get_ability_range. |
| `get_cast_delay_fraction` | `HERO_LIB.get_cast_delay_fraction(ability: Ability) -> number` | safe | Cast-delay progress in [0, 1] from the cast start time and the AbilityCastDelay property. CHANGED: 0 (was 1) outside the cast delay and for an ability with no cast delay. |
| `has_ability` | `HERO_LIB.has_ability(name: string) -> boolean` | safe | True if the local hero owns an ability whose class matches `name` (AbilityComponent class-name scan). |
| `is_on_ground` | `HERO_LIB.is_on_ground(pawn?: PlayerPawn) -> boolean` | safe |  |
| `get_stamina` | `HERO_LIB.get_stamina() -> number\|nil` | safe | The local hero's stamina pool now (the dash / air-move charges); nil without a local hero. |
| `max_stamina` | `HERO_LIB.max_stamina() -> number\|nil` | safe | The local hero's stamina pool size; nil without a local hero. |
| `get_dash_jump_state` | `HERO_LIB.get_dash_jump_state(pawn: PlayerPawn) -> table\|nil` | safe | Engine dash-jump window { can_dash_jump, window_start, window_end, consecutive_air_dashes, ok }. Same read the INNATE.DASH_JUMP precondition uses. Reads the same action record as native automation. |
| `INNATE` | `.INNATE: table` | safe | Innate action ids: LIGHT_MELEE, HEAVY_MELEE, PARRY, SLIDE, JUMP, MANTLE, ZIPLINE, DASH_JUMP. |
| `innate_count` | `.innate_count: integer` | safe | Number of innate actions. |
| `innate_ready` | `HERO_LIB.innate_ready(action: integer) -> boolean` | safe | Can this innate fire right now? (parry off cooldown, dash jump inside its window, slide grounded+moving, melee not mid-swing...) |
| `innate_press` | `HERO_LIB.innate_press(cmd: UserCmd, action: integer) -> boolean` | safe | Perform the innate on this tick's command. Presses the real input bit and arms its hold. false = the precondition failed and nothing was pressed. |
| `innate_holding` | `HERO_LIB.innate_holding(action: integer) -> boolean` | safe | True while the innate's hold is still running (heavy melee still charging). Wait on this before advancing a combo step. |
| `innate_release_all` | `HERO_LIB.innate_release_all()` | safe | Drop every innate hold (combo aborted). |
| `innate_info` | `HERO_LIB.innate_info(action: integer) -> table\|nil` | safe | { name, bits, charged, hold_seconds, delegated } for an innate action. |
| `innate_for_melee_kind` | `HERO_LIB.innate_for_melee_kind(melee_kind: integer) -> integer` | safe | Randomized-melee step kind (1 = light, 2 = heavy) -> the innate action index. -1 = not a melee step. |
| `lp_hero_id` | `HERO_LIB.lp_hero_id() -> integer` | safe |  |
| `is_channeling_ability` | `HERO_LIB.is_channeling_ability(ability: Ability) -> boolean` | safe |  |
| `get_target_pos` | `HERO_LIB.get_target_pos(target: PlayerPawn, lead?: boolean) -> Vector3\|nil` | safe | The target's body point, led two ticks on its networked velocity (lead = false returns the point itself). The point follows Umbrella's bone order: the root while burrowed, the spine of a hex / cat / Baba rig, else the mid-torso aim centre. nil when the frame holds no row for the pawn. |
| `predict_target` | `HERO_LIB.predict_target(target: PlayerPawn, lead?: boolean) -> Vector3\|nil` | safe | Same function as get_target_pos. |
| `get_origin` | `HERO_LIB.get_origin(pawn: PlayerPawn) -> Vector3` | safe | The same value as pawn:get_origin(): the per-tick origin on the game thread, the live interpolated origin off it. nil for an invalid pawn. CHANGED: used to be a live read that could differ from pawn:get_origin() inside the same callback. |
| `get_velocity` | `HERO_LIB.get_velocity(pawn?: PlayerPawn) -> Vector3` | safe | Velocity (units/s) from this tick's EntityFrame (once per tick) of the pawn, default the local pawn; (0, 0, 0) when the frame does not hold it. |
| `get_heroes_in_radius` | `HERO_LIB.get_heroes_in_radius(pos: Vector3, radius: number, opts?: table) -> PlayerPawn[]` | safe | radius is in game UNITS, NOT meters (convert a meters value with HERO_LIB.METERS_TO_UNITS first). Without opts: every hero pawn the frame holds within radius of pos. With opts { allies, enemies, visible_only, active_only, predict_s, include_local }: living, non-dormant heroes other than the local one (unless include_local); allies / enemies pick the sides (both when neither is named); visible_only keeps those seen from the local eye; active_only drops is_inactive_target pawns; predict_s measures each hero where simulate_movement_for_duration puts it after that many seconds. |
| `entities_by_class` | `HERO_LIB.entities_by_class(class_slug: string, opts?: table) -> table[]\|nil` | safe | By-CLASS entity query over the per-tick entity frame — the ONLY path to a non-pawn entity (turret / trap / soul / breakable / projectile). `class_slug` is an entity-class slug (the value the Heroes page's "Entity class" target dropdown stores). Rows are NEAREST FIRST: { pos (the class's declared aim point), origin, dist (units), handle, team, enemy, mine (the local pawn threw/owns it), visible (only when opts.require_visible), class, pawn (the `players` class only) }. opts = { origin:Vector3, max_range_u, team="enemy"\|"ally"\|"any", mine, require_visible, limit }. Returns NIL (not an empty table) when the slug is not a known class, so a bad config reports itself. |
| `should_ignore_target` | `HERO_LIB.should_ignore_target(pawn: PlayerPawn) -> boolean` | safe | Does the user's IGNORE list reject this pawn? The same ScriptHelpers::ShouldIgnoreTarget filter find_combo_target applies to every candidate. Any pick made OUTSIDE find_combo_target (a radius scan, a fallback) must ask this or it can return a hero the user told the aimbot to ignore. An invalid pawn ignores (fail-closed). |
| `get_fov_to_pos` | `HERO_LIB.get_fov_to_pos(pos: Vector3, opts?: table) -> number` | safe | Degrees between the view and the point; 180 before the first local capture. Every aim cone is a radius in this unit. Optional opts { from, angles, only_yaw } replace the camera position, the view angles and the pitch rule (only_yaw: both pitches count as 0). |
| `is_pos_within_fov` | `HERO_LIB.is_pos_within_fov(pos: Vector3, fov: number, opts?: table) -> boolean` | safe | true when the point is at most `fov` degrees from the view (a cone radius, default 45), the gate every aim cone uses. opts as get_fov_to_pos. |
| `no_obs_to_pos` | `HERO_LIB.no_obs_to_pos(from: Vector3, to: Vector3, target?: Entity, allowed?: number) -> boolean` | safe | is_line_free from `from` to `to`: an enemy body in the line blocks it, `target` (any entity) counts as clear, teammates and the local hero do not count; free when the fraction reaches `allowed` (1). Off the game thread the published visibility answers. CHANGED: an engine trace on the game thread. |
| `no_obs_to_target` | `HERO_LIB.no_obs_to_target(target: PlayerPawn, from?: Vector3, allowed?: number) -> boolean` | safe | The line from `from` (the camera by default) to the pawn's body point, as no_obs_to_pos with the pawn as target. |
| `get_hitbox_aim` | `HERO_LIB.get_hitbox_aim(target: PlayerPawn, hitbox_bits: integer) -> Vector3\|nil` | safe | Resolve a Hitbox-widget bitfield (bits 0-4 enabled Head/Neck/Torso/Arms/Legs, bits 5-9 priority) to the picked bone's world position. nil = bones not resolvable this frame. Needs the target in the aim set: nil for one tick at first sight, and always for allies and the local pawn. |
| `resolve_aim_point` | `HERO_LIB.resolve_aim_point(target: PlayerPawn, opts: table) -> Vector3\|nil` | safe | The Heroes-page "Point mode" aim point, all five modes: opts = { mode = 0 Hitboxes \| 1 Bone \| 2 Height offset \| 3 Closest surface \| 4 Origin, bits (the hitbox bitfield, modes 0/3), bone (a model bone NAME, mode 1), z (units, mode 2) }. Mode 3 returns the point on the picked hitbox's SURFACE nearest the cast ray — the aim point that minimises the PSilent camera-position offset. nil = unresolvable; the caller keeps its own fallback. Hitbox modes (0, 3) need the target in the aim set: nil for one tick at first sight, and always for allies and the local pawn. |
| `predict_projectile` | `HERO_LIB.predict_projectile(check_obstruction: boolean, info_from: integer, sim_tier: integer, aim_to_pos: integer, target: PlayerPawn, ability: Ability, caster?: PlayerPawn, opts?: table) -> (Vector3\|nil, Vector3, table, table, number, boolean)` | safe | Projectile lead solver. ARG ORDER IS EXACT: check_obstruction (ignored), info_from = ENUM_PPS_INFO_FROM (0 PROJECTILE / 1 GUN), sim_tier = ENUM_MV_SIM_TYPE, aim_to_pos = ENUM_PPS_AIM_TO_POS, then target, ability, optional caster (defaults to local pawn). Trailing opts = { speed=, radius=, hitbox= } — the hitbox bitfield goes HERE, NOT positionally. Returns aim_pos, sim_pos, traj, path, lead_time, blocked. aim_pos is nil when there is no solution. lead_time (5th) = PHYSICAL flight-time lead in SECONDS, NO ping term (native prediction is latency-blind by design; add net_channel.latency yourself for total lead). blocked (6th) = TRUE when the shot was VETOED: its trajectory (swept with the ability's real radius, arc-aware) would hit world geometry before reaching the target, or the target won't be hittable at the predicted impact (rounded a corner). blocked=true means DO NOT CAST (hold/skip); a plain nil aim_pos with blocked=false is a benign miss (fall back to a static point). The target velocity is the frame's smoothed (EMA) velocity, updated once per tick. With hitbox bits the target must be in the aim set: nil for one tick at first sight, and always for allies and the local pawn. |
| `predict_projectile_simulated` | `HERO_LIB.predict_projectile_simulated(check_obstruction: boolean, info_from: integer, sim_tier: integer, aim_to_pos: integer, target: PlayerPawn, ability: Ability, caster?: PlayerPawn, opts?: table) -> (Vector3\|nil, Vector3, table, table, number, boolean)` | safe | ALIAS of predict_projectile — the SAME function pointer (&PredictProjectileImpl), not a separate simulated solver. Same exact 8-arg signature (hitbox goes in the trailing opts table, not positionally). 5th return lead_time = flight-time lead in SECONDS, no ping term. 6th return blocked = the collision/visibility VETO (true = trajectory hits world geometry / target not hittable at impact = DO NOT CAST). Same velocity and aim-set notes as predict_projectile. |
| `bullet_gravity` | `HERO_LIB.bullet_gravity() -> number` | safe | The local weapon's bullet drop in units/s^2 (m_flBulletGravityScale x sv_gravity, 800 on standard servers; 0 without a local controller). The BASE scale, without a gravity-by-distance curve (Rat King); prediction.gravity(nil, distance) gives the effective value for a shot that long. weapon_stats().gravity is the same value. |
| `hull_projectile_will_hit` | `HERO_LIB.hull_projectile_will_hit(from: Vector3, pos: Vector3, target?: Entity, ability?: Ability\|integer, ignore_team?: boolean, radius?: number) -> boolean` | safe | A box of +-radius swept from `from` to `pos` through the local pawn reaches `pos` or stops on `target`; teammates pass through it with ignore_team. radius defaults to the ability's projectile hull (its physics radius, else its weapon's bullet radius vs the world). false for a radius outside (0, 1e5] and off the game thread. CHANGED: registered again (it was documented but not installed). |
| `throwable_aim` | `HERO_LIB.throwable_aim(with_arc?: boolean) -> table\|nil` | safe | The ability or throwable item the local hero is aiming, from the producer the projectile visuals read: { active, generation, ability (entity index), ability_hash, slot, origin, landing, normal, radius, flight_time (seconds), distance (units), hits_world, arc_count }; nil while nothing is aimed. with_arc adds arc = { Vector3, ... } (one table per point). arc_count 0: the ability has no projectile and landing is the placement point. |
| `threat` | `HERO_LIB.threat(kind?: string) -> table\|nil` | safe | The live threat that concerns the local hero (a modifier on it, or an enemy cast within reach) with the nearest answer point, from the threat feed the counter-spell detector fills: { id (unique per threat), kind ("ult", "cc" or "other"), cc, ult (an ultimate that stuns is both), source (the enemy's entity index, -1 unknown), eta_ms (until the detector's answer point, 0 once reached), hit_ms (until the hit lands, >= eta_ms, 0 once it has), slot (the source ability's signature slot 0-3; -1 item or unknown), projectile (entity index of the projectile for a projectile threat, -1 otherwise), age_ms (since detection), ability (the detector key, e.g. "infernus_ult"; "projectile" for a projectile with no Counter Spell row of its own), on_me, answered, enabled (the user's Counter Spell row for the key) }; nil when there is none. kind "cc" or "ult" keeps only threats of that class; any other string raises. A threat stays live until 800 ms past its answer point. Each call keeps the detector armed for about 2 s. While the Auto Dodge feed is armed (HERO_LIB.dodger_arm) projectile threats are included. Any thread. CHANGED: hit_ms, slot, projectile and enabled are new, and projectile rows appear. |
| `threat_answer` | `HERO_LIB.threat_answer(id: integer, gate_ok: boolean) -> boolean` | safe | Safety's reaction delay for answering threat id (the latch Counter Spell's responses use): call it every tick the answer is due, with gate_ok the action gate's verdict for the pressing action; true once that has held for the sampled human delay (at once with Safety off), and from then on the threat reads answered = true for every reader. false off the game thread and for an id no longer in the feed (the 8 newest are kept); a non-integer id raises. |
| `predict_lead_point` | `HERO_LIB.predict_lead_point(target: PlayerPawn, ability_or_speed: Ability\|number, info_from?: integer, hitbox_bits?: integer, radius_override?: number, backtrack?: boolean) -> Vector3\|nil, boolean` | safe | With an ability: the projectile solve's aim point on the target (info_from ENUM_PPS_INFO_FROM, default 1 GUN; hitbox bits as get_hitbox_aim takes them); with backtrack the target point starts at its backtrack record (the aim preset's window), and the second result says whether a record was used. With a speed: the constant-velocity lead of the target's torso from the local eye. |
| `simulate_pawn_movement` | `HERO_LIB.simulate_pawn_movement(target: PlayerPawn, sim_type?: integer, ticks_or_stop?: integer\|function) -> Vector3[]\|nil` | safe | The pawn's position after each game tick; nil without a pawn the newest frame holds. sim_type ENUM_MV_SIM_TYPE.SIMULATE_MOVEMENT (0, the default) runs the aimbot's target movement: air control and drag, sv_gravity, landing on and sliding along the map; SIMPLE (1) follows the velocity. A number is the tick count (default 1, at most 256 and 4.8 s); a function is called with (position, tick) after each tick and ends the run by returning true. |
| `simulate_movement_for_duration` | `HERO_LIB.simulate_movement_for_duration(target: PlayerPawn, duration: number, sim_type?: integer) -> Vector3\|nil` | safe | Where simulate_pawn_movement's sim puts the pawn after duration seconds (at most 4.8 s); nil without a pawn the newest frame holds. |
| `rotate_movement` | `HERO_LIB.rotate_movement(vec: Vector3, degrees: number) -> Vector3\|nil` | safe | vec turned about the vertical axis by degrees, counter-clockwise seen from above (the yaw convention); nil when vec is not a vector. |
| `is_untargetable` | `HERO_LIB.is_untargetable(pawn: PlayerPawn) -> boolean` | safe | TECH_UNTARGETABLE_BY_ENEMIES state OR any invulnerability modifier (Ethereal Shift, Haze phase-out, Viscous cube, Wrecker, Metal Skin, Prism Blast, Vyper ult, ...). The modifier names make it work on enemies. State bit and modifier flags come from this tick's EntityFrame snapshot (once per tick; false for a pawn the frame does not hold). |
| `is_stunned` | `HERO_LIB.is_stunned(pawn?: PlayerPawn) -> boolean` | safe | STUNNED state of the pawn (default: local pawn). is_stunned, is_silenced, is_frozen, is_disabled, is_state_enabled and every is_<state> / has_<state> / <state>_disabled accessor read this tick's EntityFrame state mask: refreshed once per tick, all clear for a pawn the frame does not hold or holds dead or dormant. |
| `is_in_ethereal_shift` | `HERO_LIB.is_in_ethereal_shift(pawn: PlayerPawn) -> boolean` | safe | The Ethereal Shift bubble modifier is on this pawn (by modifier name, so it works on enemies). CHANGED: used to test the INVULNERABLE state, which matched any invulnerability and missed the shift when that bit was absent. |
| `has_los` | `HERO_LIB.has_los(pawn: PlayerPawn) -> boolean` | safe | Line of sight from your eye to the pawn's head (+64) or body centre (+40). Clear only when the trace hits the pawn or travels more than 99.9% of the way. Does not yet honour smoke or other LoS-only blockers. CHANGED: the feet probe and the 97% tolerance are gone. |
| `get_ability` | `HERO_LIB.get_ability(slot: integer, pawn?: PlayerPawn) -> lightuserdata\|nil` | safe | The ability in this EAbilitySlots_t slot (0..3 = ability 1..4, 4..7 = active items, 21 = primary weapon) on pawn (default: local pawn), as light userdata every HERO_LIB ability function accepts. CHANGED: used to index the ability vector. |
| `get_item` | `HERO_LIB.get_item(slot: integer) -> lightuserdata\|nil` | safe | The local hero's active item in slot 4..7, else nil. CHANGED: used to accept vector indices 4..15. |
| `aim_psilent_default` | `HERO_LIB.aim_psilent_default(cmd: UserCmd, target_pos: Vector3, ...) -> boolean` | safe | Optional trailing Ability names the cast (bus owner + early release). |
| `aim_psilent` | `HERO_LIB.aim_psilent(cmd: UserCmd, target_pos: Vector3, ...) -> boolean` | safe |  |
| `psilent_bus_settled` | `HERO_LIB.psilent_bus_settled() -> boolean` | safe | PSilent camera is free: no cast in flight. Gate a combo step on it. |
| `cast_ability` | `HERO_LIB.cast_ability(cmd: UserCmd, ability: Ability\|integer, alt_cast?: boolean, confirm_attack?: boolean, slot_override?: integer) -> boolean` | safe | One step of casting the ability by the player's casting mode. Instant / Quick: pulse the slot's button, or release it while the ability is already selected (the release casts it). Confirm: pulse the button to select, then the Fire edge when confirm_attack. alt_cast holds the alternate-cast button; slot_override presses that slot's button instead. The older cast_ability(slot) form works on this tick's command. false when the slot has no button or nothing was pressed or released this tick. CHANGED: it used to press the slot bit only. |
| `is_heavy_melee` | `HERO_LIB.is_heavy_melee(pawn: PlayerPawn) -> boolean` | safe | True while this pawn is mid heavy-melee. Checks the modifier STATE first (works on ENEMIES), then falls back to the HoldMelee ability's attack type/state (more precise, but only ever populated for the LOCAL/spectated player — see is_heavy_melee_charging). |
| `is_heavy_melee_charging` | `HERO_LIB.is_heavy_melee_charging(pawn: PlayerPawn) -> boolean` | safe | True while this pawn is winding up / dashing a HEAVY melee. THE signal to arm an auto-parry on, and the only one that works on ENEMIES. Derived from the entity frame's modifier state (state mask) (MODIFIER_STATE_IS_IN_CHARGE_MELEE=299 / IN_SLIDE_CHARGED_MELEE_ATTACK=199, both verified against the live client.dll enum table). Do NOT use HERO_LIB.melee_state().type/.state for an enemy: those fields are MNetworkUserGroup='LocalPlayerOwnerAndObserversExclusive', i.e. the server only sends them to the ability's OWNER and that owner's spectators, so for an enemy they read 0/None forever at a perfectly correct offset. Every other field on CCitadel_Ability_HoldMelee (m_flStateStartTime, m_flDashStartTime, m_nLightChainCount) has the same user group, and m_bCreatedChargeEffects/m_angForced/m_vGoalDir are not networked at all — there is no readable field alternative. |
| `modifier_state_bits` | `HERO_LIB.modifier_state_bits(pawn?: PlayerPawn) -> integer` | safe | DIAGNOSTIC: modifier states 0-31 of the pawn (default: local pawn) as one bitmask, from this tick's EntityFrame state mask (refreshed once per tick; 0 for a pawn the frame does not hold or holds dead or dormant). enabled_state_bits lists every enabled ordinal. |
| `pawn_health` | `HERO_LIB.pawn_health(pawn: PlayerPawn) -> integer` | safe | Health from this tick's EntityFrame snapshot (once per tick); 0 for a pawn the frame does not hold. pawn_max_health, pawn_valid, pawn_team, local_team, pawn_velocity, pawn_flags, speed, speed_2d, is_lethal_dmg, hp_after_dmg, overkill, dmg_to_kill, team_of, same_team, is_enemy_of, predict_pawn_position and predict_self_position read the same snapshot. |
| `enemies_in_radius` | `HERO_LIB.enemies_in_radius(pos?: Vector3, radius?: number) -> lightuserdata[]` | safe | Living enemy (or neutral-team) pawns within radius UNITS (default 1000) of pos (default: the local pawn's origin), at most 32, as LIGHT USERDATA (pass them to HERO_LIB functions; they have no methods). enemies_alive, allies_alive, allies_in_radius, nearest_enemy_alive, lowest_hp_enemy, best_target_in_cone, enemy_lowest_hp_in_radius, enemy_hp_sum, count_alive_enemies, count_alive_allies and count_allies_in_radius scan the same once-per-tick EntityFrame snapshot. |
| `distance_to_target` | `HERO_LIB.distance_to_target(pawn: PlayerPawn) -> number` | safe | Engine distance in UNITS from the local camera to the pawn's eye, from this tick's EntityFrame (once per tick); 0 when the frame does not hold the pawn. dist_to_local is the same function. |
| `pawn_eye` | `HERO_LIB.pawn_eye(pawn: PlayerPawn) -> Vector3\|nil` | safe | The pawn's eye (origin + view offset, else 64 units above the origin) from this tick's EntityFrame; nil for a pawn the frame does not hold. |
| `pawn_by_index` | `HERO_LIB.pawn_by_index(index: integer) -> lightuserdata\|nil` | safe | The player pawn at this entity index in this tick's EntityFrame, else nil. |
| `hero_name` | `HERO_LIB.hero_name() -> string` | safe | The local hero's display name, from the hero id captured each tick; "Unknown" without a local controller. |
| `is_kali` | `HERO_LIB.is_kali() -> boolean` | safe | True while the local hero is Vyper (the game's codename for Vyper is kali). |
| `melee_range_tier` | `HERO_LIB.melee_range_tier(pawn: PlayerPawn) -> integer` | safe | This pawn's melee-range ITEM tier: 0 = none, 1 = Melee Charge, 2 = Crushing Fists. These extend a heavy melee's LUNGE DISTANCE (not its duration), so an auto-parry must add the tier's reach bonus when predicting where the punch lands — a Crushing Fists holder out-reaches the base lunge by ~140u. Non-stacking: a Crushing Fists holder also carries the Melee Charge modifier, so this returns the MAX tier and you add ONE bonus. Read from the entity frame's modifier state, built once per tick on the game thread from the exact item modifier names; use this rather than reproducing it with pawn:has_modifier(). CHANGED: used to substring-match the names. |
| `melee_in_reach` | `HERO_LIB.melee_in_reach(pawn: PlayerPawn, lead?: number) -> boolean, number, number` | safe | Whether this pawn's melee swing reaches the local hero, by the native parry engine's reach test. Returns in_reach, distance, reach in units: distance is origin to origin from the local hero to the pawn, the pawn moved `lead` seconds (default 0, clamped to [0, 1]) along its velocity; reach is the VData melee length (5 m) plus the local hero's collision radius; in_reach is distance <= reach. From the newest entity frame, lock-free, any thread. false alone for a pawn the frame does not hold alive and measured (dead, dormant, no local hero). auto_parry.lua passes two ticks plus ping as `lead`. |
| `melee_state` | `HERO_LIB.melee_state(pawn: PlayerPawn) -> table\|nil` | safe | LOCAL (and spectated) player only. { state = EMeleeHold_AttackState, type = EMeleeHold_AttackType, start_time (game seconds), charging = boolean } off the pawn's HoldMelee ability, or nil if it has none. For enemies use is_heavy_melee_charging(pawn). WARNING: state/type/start_time are ZERO FOR ENEMIES — they are MNetworkUserGroup='LocalPlayerOwnerAndObserversExclusive', so the server only sends them to the ability's owner and that owner's spectators; they are populated only for the LOCAL/spectated player. `charging` is the modifier-derived field that DOES work on enemies (same source as is_heavy_melee_charging) — use that, or is_heavy_melee_charging(pawn). |
| `telepunch_state` | `HERO_LIB.telepunch_state(ability: Ability) -> integer` | safe | Viscous Telepunch state (ETelepunchState_t) read as EXACTLY one byte — the generic Ability.__index over-reads this uint8_t enum as int32 (folds in 3 adjacent bytes). Pass the CCitadel_Ability_Viscous_Telepunch ability; 0 (None) if it isn't that ability / is nil. |
| `parry_ready` | `HERO_LIB.parry_ready() -> boolean` | safe | The parry is off cooldown and not disabled. Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `parry_blocked` | `HERO_LIB.parry_blocked() -> boolean` | safe | A parry press would be refused right now (zipline, rope, channel, stun, a form, a parry-disabling modifier). The same answer as auto parry's gate. Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `has_any_particle` | `HERO_LIB.has_any_particle(pawn: PlayerPawn, ...: string\|string[]) -> boolean` | safe | Any substring matches a particle recently created on this pawn (the shared recent-particle tracker, TTL'd). Accepts EITHER an array table `has_any_particle(p, {"a","b"})` OR varargs strings `has_any_particle(p, "a", "b")` — both shapes work on every has_any_particle binding. Empty/absent list => any recent particle at all. For anything TIMING-sensitive use PlayerPawn:get_particle_age instead: this stays true for the tracker's full 3s TTL. |
| `get_combo_fov` | `HERO_LIB.get_combo_fov() -> number` | safe | The Target Selection Combo column's cone radius in degrees, before the zoom-mode factor (180 = no cone). Compare a target's angle from the view (get_fov_to_pos) against it, or pass it as find_combo_target's combo_fov. |
| `is_target_within_cone` | `HERO_LIB.is_target_within_cone(target: PlayerPawn, fov_deg: number) -> boolean` | safe | BANNED / DEPRECATED — distance-blind and tests the wrong quantity (the 5-arg form takes a COSINE, not degrees). Use HERO_LIB.psilent_reach_ok(lp, cmd, target_pos[, ability]) to gate whether a cast can actually reach the target. |
| `script_aim_on_target` | `HERO_LIB.script_aim_on_target() -> boolean` | safe | Has the shared script VISIBLE aimbot reached the point it would itself fire at (crosshair in the deadzone, not mid-flick)? Meaningful only right AFTER driving it this tick (Bus.steer_normal / a hybrid drive), so drive THEN ask. This is Hybrid's handoff trigger: run the normal aimbot to its own fire point, then let psilent deliver — a single human flick that eases to a stop, instead of the reach-boundary stop/start flip. |
| `is_channeling_specific_abilities` | `HERO_LIB.is_channeling_specific_abilities(...) -> boolean` | safe | Any of the given abilities (Ability or slot, varargs) is channeling; or (pawn, { names }): any of the pawn's abilities named in the list (class or designer names; a missing pawn is the local one). |
| `is_in_cast_delay_specific_abilities` | `HERO_LIB.is_in_cast_delay_specific_abilities(...) -> boolean` | safe | Any of the given abilities (Ability or slot, varargs) is in its cast delay; or (pawn, { names }): any named ability of the pawn inside is_ability_in_cast_delay's window, as Umbrella's does. |
| `find_combo_target` | `HERO_LIB.find_combo_target(lp: PlayerPawn\|nil, opts?: table) -> PlayerPawn\|nil` | safe | find_combo_target([cmd\|lp][, query[, query]]) -> PlayerPawn\|nil: the current cast target, then the Combo lock (Combo column with Lock on), then the column's best pick; a Combo-column pick from the ranking becomes the lock (Umbrella's prev_combo_target). query = { max_range_m, require_visible (true), combo_fov (degrees, the cone radius; the column's own cone also bounds it, the narrower wins), priority (0 Min FOV, 1 Min Distance, 2 Lowest HP, 3 Lowest HP %), column ("items" for the Items column, else Combo) }. Honors the user's ignore rules and the visibility gate, so a pick made outside it must ask should_ignore_target. Use it from on_createmove: inside the game tick it picks (and may set the lock); outside it (on_draw) it returns the column's pick from the last two ticks, read-only, or nil. CHANGED: without max_range_m only the column's own distance applies (it was 50 m); the eye / view are internal and `bone` is no longer read. |
| `can_combo` | `HERO_LIB.can_combo(lp?: PlayerPawn, cmd?: UserCmd, allow_cursor?: boolean) -> boolean` | safe | The local hero is alive, can cast and the game has focus, and the cursor is not free (ability wheel, shop) on cmd (this tick's when omitted) unless allow_cursor. Outside the game tick (on_draw) no command is read, so the cursor gate does not apply there. CHANGED: the free-cursor gate is new. |
| `passive_items` | `HERO_LIB.passive_items() -> boolean` | safe |  |
| `combo_active` | `HERO_LIB.combo_active(bind: MenuNode) -> boolean` | safe | Combo running this tick (hold/perma). |
| `combo_active_latched` | `HERO_LIB.combo_active_latched(bind: MenuNode, timeout?: number) -> boolean` | safe | One-press-runs-the-whole-combo latch. |
| `combo_latch` | `HERO_LIB.combo_latch(state: table, active_now: boolean, timeout?: number) -> boolean` | safe | Explicit latch for step machines. |
| `combo_keepalive` | `HERO_LIB.combo_keepalive(state?: table)` | safe | Hold the stuck-clock during a long charge. |
| `combo_interrupt_status` | `HERO_LIB.combo_interrupt_status() -> string\|nil` | safe | "fatal"\|"blocked"\|nil. |
| `clear_sticky_target` | `HERO_LIB.clear_sticky_target()` | safe | Drop the persisted combo target + generation. |
| `run_combo_sequence` | `HERO_LIB.run_combo_sequence(state: table, fns: function[]) -> boolean` | safe | Step-cycling one-per-tick fall-through. |
| `is_busy` | `HERO_LIB.is_busy() -> boolean` | safe | Local hero mid-action (busy with an action, casting, channelling). Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `is_cc` | `HERO_LIB.is_cc() -> boolean` | safe | Local hero hard-disabled (stunned, asleep, frozen, chained and similar). Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `recently_cast` | `HERO_LIB.recently_cast(ability: Ability, recovery?: number) -> boolean` | safe | Charge-dump spacing guard — FALSE for any non-charge ability; use time_since_cast to ask 'did we just cast this?'. |
| `time_since_cast` | `HERO_LIB.time_since_cast(ability: Ability) -> number` | safe | Seconds since the cast began, -1 if never cast. Charge-independent. |
| `fired_this_combo` | `HERO_LIB.fired_this_combo(ability: Ability) -> boolean` | safe | One fire per ability per discrete combo. |
| `ability_in_range` | `HERO_LIB.ability_in_range(lp: PlayerPawn, ability: Ability, target: PlayerPawn, extra_m?: number) -> boolean` | safe | Real cast range + slack (fail-open). |
| `lock_on_ready` | `HERO_LIB.lock_on_ready(lp: PlayerPawn, cmd: UserCmd, ability: Ability, target: PlayerPawn, extra_m?: number) -> boolean` | safe | Range AND camera-position psilent reach. |
| `cast_origin` | `HERO_LIB.cast_origin(lp: PlayerPawn) -> Vector3` | safe | ability_cast attachment (or origin+eye). |
| `get_ability_range` | `HERO_LIB.get_ability_range(ability: Ability\|integer) -> number` | safe | Scaled cast range in UNITS, including cast-range items; 4000 when the ability declares none. Alias of get_cast_range. A number is an EAbilitySlots_t slot. |
| `lethal_estimate` | `HERO_LIB.lethal_estimate(target: PlayerPawn, damage: number) -> boolean` | safe | true when target HP > 0 and damage >= HP+barrier. Also accepts the is_lethal form (ability, target[, seconds_until_hit]). CHANGED: the barrier was ignored. |
| `is_lethal` | `HERO_LIB.is_lethal(ability: Ability, target: PlayerPawn, seconds_until_hit: number?) -> boolean` | safe | Ability resolved damage vs effective HP (post-resist damage vs current HP+barrier). Optional seconds_until_hit projects the target's HP forward by its passive regen over that window (a charge/scope hold, projectile travel) so an execute won't fire on a target that heals out of lethal range by impact; omit/0 = current HP. The legacy form is_lethal(target:PlayerPawn, damage:number) compares a raw damage number with HP+barrier. CHANGED: the ability form raised "bad argument #2" on every call. |
| `lethality` | `HERO_LIB.lethality(ability: Ability, target: PlayerPawn, seconds_until_hit: number?) -> table\|nil` | safe | The NUMBERS behind is_lethal: { damage (post-resist, one FULL cast, INCLUDES the headshot bonus), headshot_bonus (the head-shot-only slice of damage; damage-headshot_bonus = the BODY-shot damage; 0 if no headshot mechanic), hp (current+barrier, regen-projected over seconds_until_hit), remaining, lethal, valid }. Lets a charge-up ability invert 'how much charge kills this target' and lets a sniper choose center-mass vs head by whether the body shot alone is lethal. Optional seconds_until_hit matches is_lethal (heal projection). valid=false => damage unresolvable, do not gate. nil when ability or target is invalid. lethality(target:PlayerPawn, damage:number?) fills the same table from a raw damage number (headshot_bonus 0). CHANGED: returned only {hp, max_hp}. |
| `headshot_cap_ok` | `HERO_LIB.headshot_cap_ok(max_percent: number) -> boolean` | safe | May a script aim at the HEAD right now? The same stat test the aimbot's own bone selection applies (CanTargetHeadBasedOnDamageStats); false => drop Head+Neck from the mask. |
| `vdata_property` | `HERO_LIB.vdata_property(ability: Ability, vdata_class: string, field: string) -> number\|nil` | safe | A float field on the ability's VDATA, by schema CLASS + NAME (e.g. "CAbilityHornetSnipeVData", "m_flMinScopeTimeToShoot"). ability:get_vdata() only projects m_projectileInfo/m_WeaponInfo, so every other authored VData number is unreachable without this. The class name is explicit because a VData object carries no schema binding to ask. Offset resolved through the LIVE schema. nil = unknown class/field. |
| `maybe_light_melee` | `HERO_LIB.maybe_light_melee(cmd: UserCmd, chance: number, key?: string) -> boolean` | safe | Roll-once light-melee humanizer. |
| `reset_light_melee` | `HERO_LIB.reset_light_melee(key: string)` | safe | Open a fresh melee roll window. |
| `press_ability` | `HERO_LIB.press_ability(cmd: UserCmd, ability: Ability\|integer, alt_cast?: boolean, confirm_attack?: boolean, slot_override?: integer) -> boolean` | safe | Same function as cast_ability. |
| `slot_ability_bit` | `HERO_LIB.slot_ability_bit(slot: integer) -> number` | safe | slot 0..3 -> IN_ABILITYn bit. |
| `meters_to_units` | `HERO_LIB.meters_to_units(m: number) -> number` | safe |  |
| `begin_combo_tick` | `HERO_LIB.begin_combo_tick(cmd: UserCmd, hero_id: integer, enable: boolean, bind: MenuNode, opts?: table) -> PlayerPawn\|nil, PlayerPawn\|nil` | safe | Createmove prologue: returns lp,target. |
| `run_projectile_ability` | `HERO_LIB.run_projectile_ability(cmd: UserCmd, target: PlayerPawn, lp: PlayerPawn, opts: table) -> boolean` | safe | Full projectile-ability pipeline in one call. |
| `abilities_ready` | `HERO_LIB.abilities_ready() -> boolean` | safe | INIT-TIMING honesty signal. False in the brief post-inject / post-hero-swap window where the local pawn already exists (hero-id resolution already works then) but the game hasn't yet populated its ability component with slotted signature abilities — the exact gap behind 'can_use_ability/ability_true_cooldown read wrong right after injecting'. LIVE, not cached: nothing to call to force it — once this returns true, re-querying can_use_ability/ability_true_cooldown/can_activate() returns correct data on its own. Checks only the 4 signature slots (every hero always has them); items are excluded since an empty item slot can be legitimately unowned all match. |
| `can_use_ability` | `HERO_LIB.can_use_ability(slot: integer) -> boolean` | safe | Authoritative yes/no for signature slot 1..4 (game's own cast-validity). slot is 1-INDEXED here (as are can_use_item / item_true_cooldown / can_place_*_on) — note that ability_slot(), ability_true_cooldown(slot), get_ability(slot), SlotInputBit and the aim `slot` arg take the 0-INDEXED game slot (0..3 = ability 1..4). |
| `can_use_item` | `HERO_LIB.can_use_item(pawn?: PlayerPawn) -> boolean` | safe | The hero can use an item now: covers mute, stun, sleep and busy. With no argument (or the local pawn) it reads the local hero's action record, the same one native automation reads, and is false while dead; another pawn answers from its modifier states. |
| `ability_true_cooldown` | `HERO_LIB.ability_true_cooldown(ability: Ability\|integer) -> number` | safe | Seconds until the ability is usable again (0 = now; >0 = next USABLE CHARGE). Accepts an Ability object (e.g. lp:get_ability_by_slot(1)), the light userdata get_ability returns, or a 0-INDEXED EAbilitySlots_t slot (0..3 = ability 1..4). CHANGED: an Ability object used to return 1e9 (never ready). |
| `item_true_cooldown` | `HERO_LIB.item_true_cooldown(slot: integer) -> number` | safe | Seconds until active-item slot 1..4 is usable again (0 = now; >0 = next USABLE CHARGE). |
| `can_place_ability_on` | `HERO_LIB.can_place_ability_on(slot: integer, entity: PlayerPawn) -> boolean` | safe | Targeting validity for signature slot 1..4 on a candidate entity: team/type (ally/enemy/self) + range + cone + LOS, from the ability's own vdata. Per-target companion of can_use_ability. READ-ONLY. |
| `can_place_item_on` | `HERO_LIB.can_place_item_on(slot: integer, entity: PlayerPawn) -> boolean` | safe | Targeting validity for active-item slot 1..4 on a candidate entity (same rules as can_place_ability_on). Per-target companion of can_use_item. READ-ONLY. |
| `owns_item` | `HERO_LIB.owns_item(token: string) -> boolean` | safe | Local hero owns this item now (active or passive). `token` is the exact item record name, e.g. "upgrade_kinetic_sash"; matched exactly and case-insensitively against the item's subclass identity. CHANGED: short names such as "kineticsash" no longer match. |
| `owned_item` | `HERO_LIB.owned_item(token: string) -> Ability\|nil` | safe | The OWNED item (active or passive) as an Ability object; nil if not owned. Same exact record-name token as owns_item. Use it for items instead of lp:get_ability(name), which matches the vdata _class ("upgrade_silence_glyph" for "upgrade_targeted_silence"; many items share one class). |
| `item_policy` | `HERO_LIB.item_policy(token: string, trigger?: integer, focus?: PlayerPawn) -> {use:boolean, self:boolean, target_index:integer, aim_x?:number, aim_y?:number, aim_z?:number, reason:integer}\|nil` | safe | The item's configured use policy evaluated now: use (fire it), self (self-cast), target_index (candidate entity index, -1 for none), aim_x/y/z when it has an aim point, and reason. nil for an unknown record-name token. trigger 0 = a combo step (default), 1 = the standalone pool runner; focus = this tick's combo target. Game thread (CreateMove callbacks); elsewhere use is false. |
| `combo_paused` | `HERO_LIB.combo_paused() -> boolean` | safe | Ethereal Shift's "Pause The Combo While Shifted" holds the combo now. |
| `hit_chance_pass` | `HERO_LIB.hit_chance_pass(percent: number) -> boolean` | safe | One roll against a hit chance (the aimbot's per-shot roll): true at >= 100, false at <= 0. Game thread (CreateMove callbacks); elsewhere only >= 100 passes. |
| `damage_taken` | `HERO_LIB.damage_taken(pawn: PlayerPawn, seconds?: number) -> number` | safe | Damage the pawn took in the last `seconds` (default 1). 0 when unknown. |
| `special_ult_report` | `HERO_LIB.special_ult_report(pick: integer, verdict: integer, enemies: integer, radius: number)` | safe | Publishes the hero script's special-ultimate state to the host: picked hero id (-1 for none), verdict (2 = cast, 3 = prevented, otherwise waiting), enemies in radius and the radius. |
| `item_ready` | `HERO_LIB.item_ready(token: string) -> boolean` | safe | Owned AND off cooldown / ready. Same exact record-name token as owns_item. |
| `item_range` | `HERO_LIB.item_range(token: string) -> number, number` | safe | cast_range, aoe_radius for the OWNED item, both scaled and in game UNITS (the same producers as get_cast_range / get_aoe_radius). (0,0) if not owned. Same exact record-name token as owns_item. |
| `use_item_slot` | `HERO_LIB.use_item_slot(cmd: UserCmd, token: string, target_pos?: Vector3) -> boolean` | safe | Fire the OWNED item by its CURRENT active-item slot bit (robust to runtime slot moves). If target_pos is given and non-zero the cast first wins a slot on the PSilent bus (camera POSITION only); a busy bus presses NOTHING and returns false (retry next tick). false = not owned/ready/active-item. |
| `use_item` | `HERO_LIB.use_item(cmd: UserCmd, ability: Ability) -> boolean` | safe | Fire an active ITEM instantly (self/AOE buff): resolve the item's active-item slot -> input bit and press it. false = not an active item / invalid. |
| `use_item_targeted` | `HERO_LIB.use_item_targeted(cmd: UserCmd, ability: Ability, target_pos: Vector3) -> boolean` | safe | Take a slot on the PSilent bus toward target_pos for the item's slot bit, then press it (targeted item lands on the enemy). Camera POSITION only. false = not an item / bus busy (press nothing, retry). |
| `psilent_reach_ok` | `HERO_LIB.psilent_reach_ok(lp: PlayerPawn, cmd: UserCmd, target_pos: Vector3, ability_or_slot?: Ability\|integer) -> boolean` | safe | THE sanctioned reach test: can the camera-position spoof actually CENTRE target_pos this tick? Computed by the SAME solver the applier uses (offset from the commanded-camera eye, the engine-clamp anchor) so 'can I hit?' matches 'will the spoof centre it?'. Returns true only when the needed offset <= active PSilent reach * 0.9 (a small honest-edge safety margin, so marginal shots the engine would clamp short are HELD, not fired blind). Only target_pos is required; the optional Ability/0..3 slot scopes the reach to that ability's override. USE THIS INSTEAD OF is_target_within_cone (distance-blind, wrong quantity). |
| `mark_combo_active` | `HERO_LIB.mark_combo_active()` | safe | Pulse each tick the Combo Key is held so the Bind Island shows the hero script as active only while its combo runs (key-press -> cast tail), not always-on once loaded. |
| `reset_combo_sticky` | `HERO_LIB.reset_combo_sticky()` | safe | Reset the C++ sticky combo target so the next combo re-acquires by configured priority (call on combo end). Without it the selector holds the previous combo's target across presses. |
| `ability_slot` | `HERO_LIB.ability_slot(ability: Ability) -> integer` | safe | The ability's LIVE game slot (m_eAbilitySlot): 0..3 = ability 1..4, 4..7 = active items, 21 = primary weapon; -1 if the local hero does not own it. Round-trips with get_ability(slot). Press/aim the slot the game ACTUALLY put the ability in — Deadlock reorders abilities between builds. CHANGED: used to return the ability-vector index. |
| `get_aoe_radius` | `HERO_LIB.get_aoe_radius(ability: Ability) -> number` | safe | Scaled AoE radius in game UNITS; 0 if the ability declares none. Same producer as Ability:get_aoe_radius. |
| `entity_pos_by_name` | `HERO_LIB.entity_pos_by_name(name: string) -> Vector3\|nil` | safe | World position of the first entity whose class name contains `name` (case-insensitive substring over the live entity system). nil if none / not a string. |
| `interval_per_tick` | `HERO_LIB.interval_per_tick() -> number` | safe | Seconds per simulation tick, read from the engine (~1/64). The lib's timing primitive. |
| `lp_hero_name` | `HERO_LIB.lp_hero_name() -> string` | safe | Ground-truth local hero name "<table>\|<designer>" for diagnostics (mirrors the PlayerESP hero-icon path). |
| `diag` | `HERO_LIB.diag(...)` | safe | Write ONE deduped line to C:\Avalanche\avalan-debug.log (file-only, never console). Args joined by spaces; each UNIQUE line written once. NO-OP in the protected release build. |
| `log` | `HERO_LIB.log(...)` | safe | Accepted and dropped: prints nothing (dev_notify reaches the toast channel). |
| `notify` | `HERO_LIB.notify(...)` | safe | Accepted and dropped: prints nothing (dev_notify reaches the toast channel). |
| `debug` | `HERO_LIB.debug(...)` | safe | Accepted and dropped: prints nothing (dev_notify reaches the toast channel). |
| `screen_pos` | `HERO_LIB.screen_pos(pawn: PlayerPawn) -> table\|nil` | safe | { x, y } of the pawn's feet on screen, from the screen frame. Render callbacks only: nil elsewhere, behind the camera, and on the first call for a pawn (ready from the next frame). |
| `dev_mode` | `HERO_LIB.dev_mode() -> boolean` | safe | Is verbose dev surfacing on? OFF by default (also settable at boot via env AVALANCHE_LUA_DEVMODE). When on, U.log lines + the full binding/hook/snapshot/skip diagnostics surface as in-game toasts. |
| `set_dev_mode` | `HERO_LIB.set_dev_mode(on: boolean)` | safe | Toggle verbose dev surfacing from a script or the Lua console (HERO_LIB.set_dev_mode(true)). One flag, one home; a non-zero number also counts as on. |
| `errors` | `HERO_LIB.errors() -> table[]` | safe | Bounded ring (~64, oldest-first) of recent native BINDING FAULTS, each { kind, where, script, message, time }. Lets a script read its OWN binding faults at runtime (delivers AvaLua Error.hpp's long-standing promise). Independent of dev_mode. |
| `dev_notify` | `HERO_LIB.dev_notify(text: string)` | safe | Push ONE line to the deduped, decaying (~5s), visible diagnostic toast channel — the SAME channel U.log uses when dev_mode is on. Non-string is ignored. |
| `set_combo_status` | `HERO_LIB.set_combo_status(text: string)` | safe | ENGINE-INTERNAL / ADVANCED: publish this tick's 'why the combo is waiting/skipping' reason for the Bind Island (e.g. "waiting (bus)" / "skipped (cooldown)"). Not a toast (no per-tick spam); render-thread reads it for a 0.5s tail. Empty/nil clears. |
| `set_can_kill_indicator` | `HERO_LIB.set_can_kill_indicator(hero_id: integer, slot: integer, indices: integer[])` | safe | ENGINE-INTERNAL / ADVANCED: the can-kill ult-icon signal. Call every tick from an always-on feature's on_tick with the ARRAY of killable enemy ENTRY indices (pawn:get_index()): the ESP renderer draws hero_id's ability-slot icon (the ult) accent-tinted over EACH of those enemies, anchored to its ESP box at the user's dragged box-relative offset. An empty/absent array clears it; the signal expires (~0.3s) so a feature toggled off / death / hero swap clears the badge on its own. The menu's Kill Indicator settings (Show For, Confidence, Two-Shot Tail, Max Shown) extend and rank the list. Only plain ints cross the thread boundary (thread-safe). |
| `UNITS_TO_METERS` | `.UNITS_TO_METERS: number` | safe | Meters per game unit (0.0254, the engine constant; 1 unit = 1 inch). Multiply units by this to get meters. |
| `METERS_TO_UNITS` | `.METERS_TO_UNITS: number` | safe | Game units per meter (reciprocal of UNITS_TO_METERS). |
| `ENUM_MV_SIM_TYPE` | `.ENUM_MV_SIM_TYPE: table` | safe | Movement-sim type enum { SIMULATE_MOVEMENT = 0, SIMPLE = 1 } for simulate_movement_for_duration. |
| `ENUM_PPS_INFO_FROM` | `.ENUM_PPS_INFO_FROM: table` | safe | Projectile-info source enum { PROJECTILE = 0, GUN = 1 }. |
| `ENUM_PPS_AIM_TO_POS` | `.ENUM_PPS_AIM_TO_POS: table` | safe | Predict-projectile aim-to enum { PAWN_ORIGIN = 0, LIB_TARGET_POS = 1 }. |
| `can_move` | `HERO_LIB.can_move(pawn?: PlayerPawn) -> boolean` | safe | The hero can move now (asleep still counts: the game allows a slow walk). With no argument (or the local pawn) it reads the local hero's action record, the same one native automation reads, and is false while dead; another pawn answers from its modifier states. |
| `can_attack` | `HERO_LIB.can_attack(pawn?: PlayerPawn) -> boolean` | safe | The hero can shoot now: false while reloading or with an ability selected. With no argument (or the local pawn) it reads the local hero's action record, the same one native automation reads, and is false while dead; another pawn answers from its modifier states. |
| `can_cast` | `HERO_LIB.can_cast(pawn?: PlayerPawn) -> boolean` | safe | The hero can cast an ability now (not silenced, stunned, busy or channelling). With no argument (or the local pawn) it reads the local hero's action record, the same one native automation reads, and is false while dead; another pawn answers from its modifier states. |
| `is_reloading` | `HERO_LIB.is_reloading(pawn?: PlayerPawn) -> boolean` | safe | The hero is reloading. With no argument (or the local pawn) it reads the local hero's action record, the same one native automation reads, and is false while dead; another pawn answers from its modifier states. |
| `is_flying` | `HERO_LIB.is_flying() -> boolean` | safe | Local hero is in a flight form or flying ability movement. Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `is_using_zipline` | `HERO_LIB.is_using_zipline() -> boolean` | safe | Local hero rides a zipline. Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `is_using_zipline_boost` | `HERO_LIB.is_using_zipline_boost() -> boolean` | safe | Local hero is in the zipline boost. Reads the local hero's action record, the same one native automation reads; false while dead or without a local hero. |
| `ability_is_channeled` | `HERO_LIB.ability_is_channeled(ability: Ability) -> boolean` | safe | True when the ability is a channelled ability (its kind), not whether it is channelling now. |
| `get_ability_self_cast_delay` | `HERO_LIB.get_ability_self_cast_delay() -> number` | safe | The local hero's alternate-cast window in seconds: the hold time or the double-tap timeout of the player's alt-cast mode, 0 for the modifier-key mode. |
| `get_ability_cast_mode` | `HERO_LIB.get_ability_cast_mode(ability: Ability\|integer) -> integer\|nil` | safe | How a press of the ability's button casts it now, as HERO_LIB.QUICKCAST_MODE (the vdata activation with the player's casting-mode setting applied; DEFAULT for a passive). nil for a slot without a cast button or unreadable vdata. Any thread. |
| `get_ability_default_cast_mode` | `HERO_LIB.get_ability_default_cast_mode(ability: Ability\|integer) -> integer\|nil` | safe | The vdata activation's QUICKCAST_MODE without the player's setting; nil when unreadable. |
| `is_ability_selected` | `HERO_LIB.is_ability_selected(pawn: PlayerPawn\|nil, ability: Ability\|integer) -> boolean` | safe | The local hero has this ability selected, waiting for Fire (Confirm cast). Selection exists for the local hero only; the pawn argument is accepted and not read. |
| `get_ability_input_mask` | `HERO_LIB.get_ability_input_mask(ability: Ability\|integer) -> integer\|nil` | safe | The button of the ability's slot: IN_ABILITY1..4 for slots 0-3, IN_ITEM1..4 for 4-7; nil otherwise. |
| `pulse_button` | `HERO_LIB.pulse_button(cmd: UserCmd, mask: integer) -> boolean` | safe | cmd:pulse(mask) for HERO_LIB callers: one fresh press that releases itself on the next command; false while the mask is being released or was already pulsed, and for any command but this tick's. |
| `block_item` | `HERO_LIB.block_item(cmd: UserCmd, ability: Ability\|integer)` | safe | Clears the slot's button from all three button states, so the game does not act on it this tick. |
| `is_using_free_cursor` | `HERO_LIB.is_using_free_cursor(cmd?: UserCmd) -> boolean` | safe | The player has a free cursor (the ability wheel, the shop) on this command (this tick's when omitted). |
| `QUICKCAST_MODE` | `.QUICKCAST_MODE: table` | safe | Casting modes as get_ability_cast_mode returns them: DEFAULT 0 (passive), INSTANT 1, CONFIRM 2 (select, then Fire), QUICK 3 (cast on release). |
| `threats` | `HERO_LIB.threats(kind?: string) -> table[]` | safe | Every live threat that concerns the local hero, nearest answer point first, each in threat()'s row shape; an empty table when there is none. kind as threat(). Any thread. NEW: the projectile pick's row (projectile >= 0) also carries dir (unit travel direction), source_position (the projectile now) and after_predict_info { hit_projectile_pos, hit_projectile_velocity (units/s), aoe_center, aoe_radius (blast projectiles only) }. |
| `counter_chain` | `HERO_LIB.counter_chain(threat: table\|string) -> string[]\|nil, string, boolean` | safe | Counter Spell's answer for a threat() / threats() row or its `ability` key: chain (the response ids to try in order, e.g. "parry", "metal_skin"; empty when nothing answers it), mode ("always" \| "if_lethal" \| "never"), fallback (true when chain is the Any-threat chain because the threat has none of its own). nil while Counter Spell is off. Any thread, lock-free. |
| `get_bone_positions` | `HERO_LIB.get_bone_positions(pawn: PlayerPawn, ignore_legs?: boolean) -> table` | safe | { bone name = Vector3 } for the pawn's body bones (legs left out with ignore_legs); empty without bones. |
| `get_on_hero_indicator_pos` | `HERO_LIB.get_on_hero_indicator_pos(pawn: PlayerPawn) -> Vector3\|nil` | safe | The pawn's origin raised by ON_HERO_INDICATOR_Z_OFFSET (the origin itself while burrowed); nil when the frame has no origin for it. |
| `get_fov_to_entity` | `HERO_LIB.get_fov_to_entity(pawn: PlayerPawn, opts?: table) -> number` | safe | Smallest angle in degrees from the view to the pawn's body bones; opts { from, angles, only_yaw } as get_fov_to_pos (defaults: the local eye and view). 999 without bones or without a view. |
| `within_ability_cone` | `HERO_LIB.within_ability_cone(ability: Ability\|integer, point: Vector3, opts?: table) -> boolean, number` | safe | The point is inside the ability's own targeting cone from the local eye: inside, half-angle (degrees). opts { from_origin (measure from the feet), pitch (count pitch; yaw-only by default), half_width (use targeting_cone_half_width instead of half the cone angle), scale (multiplies the half-angle) }. |
| `get_predicted_cone_target` | `HERO_LIB.get_predicted_cone_target(cmd: UserCmd, ability: Ability\|integer, angles?: Angle\|table, filter?: function) -> PlayerPawn\|Entity\|nil` | safe | The unit a cone-targeted ability cast now would land on (Umbrella's get_predicted_cone_target): heroes and lane / jungle NPCs of the teams the ability may target, within cast range, inside the vdata cone widened by its half width, in line of sight when the vdata asks; the one closest to the aim direction. angles replaces the command's view; filter(candidate) -> boolean can reject one. Game thread for exact answers (elsewhere candidates that need LOS are rejected). |
| `is_within_wave_width` | `HERO_LIB.is_within_wave_width(from: Vector3, fwd: Vector3, point: Vector3, width_m: number) -> boolean` | safe | The point's distance from the line through `from` along unit `fwd` is at most half of width_m (meters). |
| `is_line_free` | `HERO_LIB.is_line_free(from: Vector3, to: Vector3, target?: Entity, allowed?: number) -> boolean, number` | safe | Umbrella's is_line_free: one engine line from `from` to `to` that passes through the local pawn and its teammates; the world and every entity of another team stop it. free when the fraction reaches `allowed` (1) or the line stops on `target`; the second result is the fraction. false alone when not answered (off the game thread, no local pawn, engine cast unavailable). |
| `predict_cast` | `HERO_LIB.predict_cast(target: PlayerPawn, ability: Ability\|integer, opts?: table) -> Vector3\|nil, Vector3\|nil, table` | safe | The local hero's cast of `ability` at `target` (Umbrella's predict_projectile_simulated, or with opts.ground its ground-cast prediction) on the engine movement sim: aim (the predicted point raised for drop, up speed and aim bias) or nil when no shot connects, predicted (the target point when the shot arrives) or nil, info { flight_time, mb_only (only a magic-bullet shot connects), mb_foot (its origin), path, projectile_path (debug only) }. opts { from (ENUM_PPS_INFO_FROM: 1 = the weapon info), sim (ENUM_MV_SIM_TYPE: 1 = simple), aim_to (ENUM_PPS_AIM_TO_POS, default 1 = the body point), camera_cast, ignore_z, ground, target_pos, cast_point, speed, max_range (units), aim_type (aim.type bits: MAGIC_BULLETS tries the magic-bullet origin on a blocked line), activation_delay, ground_offset, debug }. Exact on the game thread in on_createmove; elsewhere from frame reads (no line check, no aim). One solve per target, ability, options and tick. |
| `steer_movement` | `HERO_LIB.steer_movement(cmd: UserCmd, opts: table) -> boolean` | safe | Rewrites the command's forward / left / up moves so the hero moves toward opts.pos (seen from the hero), opts.dir or opts.yaw (+ opts.pitch when only_yaw = false) whatever the view (Umbrella's rotate_movement, sign-consistent). opts { only_yaw = true, forward, backward (push that way first), exclusive (clear the other move axes first) }. false with the command untouched when there is no command or no direction. Game thread, on_createmove. |
| `aim` | `HERO_LIB.aim(cmd: UserCmd, opts: table) -> integer` | safe | cmd:aim(opts) with Umbrella's smoothing compensation (never below Safety's floor); notes an enemy-hero cast target; runs the callbacks. A self-area aim (no target, a line reaching foot height within 3 m of the hero) is not refused by Safety's visible-aim cone; SILENT stays refused there. Returns aim.status. |
| `aim_status_consumes_combo` | `HERO_LIB.aim_status_consumes_combo(status: integer) -> boolean` | safe | The aim owns this tick (PENDING, AIMING, READY or BUSY): skip the rest of the combo. |
| `handle_auto_save` | `HERO_LIB.handle_auto_save(cmd: UserCmd, ability: Ability\|integer, settings: table) -> boolean` | safe | Umbrella's self / ally save on health or burst damage, with a per-ability memory of recent health loss. settings = { targets = { self, allies }, self_only, aim = { type, smooth }, max_fov, triggers = { health, health_loss }, health_mode, health_percent, health_exact, health_loss_mode, health_loss_percent, health_loss_exact, health_loss_time, target_filter } (modes "percent" \| "exact"; aim.type is aim.type bits). Self casts pass the action gate; ally saves aim with HERO_LIB.aim and confirm the cone pick before pressing. true when the save owns this tick. Game thread inside on_createmove; false elsewhere. |
| `handle_all_items` | `HERO_LIB.handle_all_items(cmd: UserCmd, target: PlayerPawn, items?: table) -> boolean` | safe | Umbrella's combo item groups in its order: target items, then AOE items, then non-target items. items = { enabled, aim = { type, smooth }, aoe = { tokens }, target = { tokens }, non_target = { tokens } }; a missing group takes Umbrella's default picks. Without items: the hero's Items switch and item pool, each pick sorted into the groups. An item already on this tick's command is skipped, every press passes the action gate, Echo Shard / Refresher only with something to refresh. true when a group acted. |
| `handle_target_items` | `HERO_LIB.handle_target_items(cmd: UserCmd, target: PlayerPawn, list?: table) -> boolean` | safe | The target-item group alone: list = { tokens } with an optional list.aim = { type, smooth }; without it, the hero's target picks while Items is on. true when an item press or its aim took the tick. |
| `spirit_damage` | `HERO_LIB.spirit_damage(target: Entity, base_damage: number, ability?: Ability) -> number, boolean\|nil` | safe | One spirit hit of base_damage from the local hero on a hero or an NPC through Umbrella's damage model (spirit amps, item procs, Spellbreaker, Escalating Exposure, resists from the engine stat, NPC objective scales): damage, blocked (nothing can land: no outgoing damage, invulnerable, out of game, spell immunity, unkillable, dead or dormant). Game thread; nil elsewhere and for a target the newest frame does not hold. |
| `predict_health` | `HERO_LIB.predict_health(target: Entity, delay?: number, add?: number, include_barrier?: boolean) -> number\|nil` | safe | Health plus regen over `delay` seconds (capped at max), plus the barrier when asked, plus `add`. Heroes on any thread; NPCs on the game thread (nil elsewhere). |
| `scaled_damage` | `HERO_LIB.scaled_damage(ability: Ability\|integer, target: PlayerPawn, count_resists?: boolean) -> table\|nil` | safe | The engine's own scaling for one hit of the ability on the target: { damage (one body hit, after resist unless count_resists = false), headshot (the headshot bonus), is_bullet (bullet resist applies, else spirit) }. Game thread; nil elsewhere or when unresolvable. |
| `engine_execute` | `HERO_LIB.engine_execute(ability: Ability\|integer, target: PlayerPawn) -> boolean\|nil` | safe | The HUD's own execute mark for the four execute kits (Shiv's killing blow, Grey Talon's guided arrow, Vindicta's snipe bonus, Venator's crossbow): true when the target carries the local caster's mark and is not unkillable. nil for other abilities, off the game thread, or when the engine check does not resolve. |
| `get_ground_autocast_remaining` | `HERO_LIB.get_ground_autocast_remaining(pawn: PlayerPawn, conditions?: table) -> number, boolean, Vector3\|nil` | safe | Seconds until a ground-autocast window opens on the pawn, whether it is protected, and the destination when known. conditions is a set { stun, victor_revive, rejuvenator, doorman_hotel, void_sphere, shadow_transformation }; a key counts while truthy; nil = every state on. |
| `get_ground_autocast_protection_timing` | `HERO_LIB.get_ground_autocast_protection_timing(remaining: number, lead: number, buffer: number, reserve: number, tick: number, teleport?: boolean) -> boolean, boolean` | safe | Umbrella's timing rule: can_aim (remaining is inside the lead - buffer + reserve window, and for a non-teleport at least two ticks out), cast_now (can_aim and remaining <= lead - buffer). |
| `project_ground_autocast_position` | `HERO_LIB.project_ground_autocast_position(pawn: PlayerPawn, pos: Vector3, ability: Ability\|integer) -> Vector3\|nil` | safe | Projects pos to the ground point the ability would land on for the pawn; nil when it cannot. |
| `find_helper_target` | `HERO_LIB.find_helper_target(cmd?: UserCmd, lp?: PlayerPawn) -> PlayerPawn\|nil` | safe | The Items column's pick of Target Selection with the current cast target preferred, memoised per command; drops the Combo lock first. nil off the game tick. |
| `is_in_mirage_tornado` | `HERO_LIB.is_in_mirage_tornado(pawn?: PlayerPawn) -> boolean` | safe | The pawn (the local one when omitted) is inside Mirage's tornado. |
| `is_inactive_target` | `HERO_LIB.is_inactive_target(pawn?: PlayerPawn) -> boolean` | safe | Not worth targeting: cubed, in stone form, out of game, invulnerable or inside Mirage's tornado. |
| `avoids_spells` | `HERO_LIB.avoids_spells(pawn?: PlayerPawn) -> boolean` | safe | A spell-immunity buff is on: a positive MODIFIER_VALUE_AVOID_SPELL sum over the pawn's modifiers. Game thread; false elsewhere. |
| `whitelist_bones_only_head_body` | `.whitelist_bones_only_head_body: table` | safe | Read-only set { [bone name] = true } of the head and body bones (no limbs); pairs() works, writes raise. |
| `ON_HERO_INDICATOR_Z_OFFSET` | `.ON_HERO_INDICATOR_Z_OFFSET: integer` | safe | 65: units above the origin get_on_hero_indicator_pos raises an over-hero indicator. |
| `lead_for` | `HERO_LIB.lead_for(from: Vector3, pos: Vector3, vel: Vector3, speed: number, ability?: Ability, ignore_z?: boolean) -> Vector3, Vector3, number` | safe | The straight-line intercept: aim, predicted, t. With an ability its projectile supplies the speed when speed is not positive, and unless ignore_z the aim point is raised by the drop (0.5 g t^2), lowered by its up speed and by its vertical aim bias. Without a speed or an intercept, aim = predicted = pos and t = 0. |

### ANIM_LIB

`table` · tier `safe` — Native animation/notification helper (frame delta, eased value ramps, centered toast). Plain global, no require.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_delta_time` | `ANIM_LIB.get_delta_time() -> number` | safe | Current frame delta in seconds (global_vars absolute frametime; floored to 1/60 when globals are unavailable). The single frame-delta source for the value ramps. |
| `centered_notification` | `ANIM_LIB.centered_notification(text: string, duration: number?) -> nil` | safe | Push a centered toast through the standard thread-safe notification queue. Empty text is ignored; duration <= 0 falls back to 3s. |
| `calculate_value` | `ANIM_LIB.calculate_value(key: string, going_up: boolean, speed: number, min: number?, max: number?) -> number` | safe | Per-key value that ramps toward max (going_up) or min at `speed` units/sec, frame-scaled and CLAMPED to [min,max] (defaults 0..1). State keyed by the string, shared across callers. |
| `calculate_value_no_clamp` | `ANIM_LIB.calculate_value_no_clamp(key: string, going_up: boolean, speed: number, min: number?, max: number?) -> number` | safe | Like calculate_value but only steps while not already at the target edge, easing an out-of-band value back into range instead of snapping. |
| `easings` | `.easings: table` | safe | Easing curves { out_quart, in_quart, in_out_quart, in_out_cubic } — each fun(t:number):number for t in [0,1]. |
| `out_quart` | `ANIM_LIB.out_quart(t: number) -> number` | safe | Quartic ease-out for t in [0,1] (flat alias of easings.out_quart). |
| `in_quart` | `ANIM_LIB.in_quart(t: number) -> number` | safe | Quartic ease-in for t in [0,1] (flat alias of easings.in_quart). |
| `in_out_quart` | `ANIM_LIB.in_out_quart(t: number) -> number` | safe | Quartic ease-in-out for t in [0,1] (flat alias of easings.in_out_quart). |
| `in_out_cubic` | `ANIM_LIB.in_out_cubic(t: number) -> number` | safe | Cubic ease-in-out for t in [0,1] (flat alias of easings.in_out_cubic). |

### Render

`table` · tier `safe` — 2D/3D drawing surface.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `DrawText` | `Render.DrawText(x: number, y: number, text: string, color: Color, fontHandle?: integer, align?: integer)` | safe | Optional Render.TEXT_ALIGN_* (default center). |
| `Text` | `Render.Text(font: integer, size: number, text: string, pos: Vec2, color: Color, align?: integer)` | safe | Font-first draw honoring the handle's family+weight at the per-call size; also accepts (x,y,text,color[,font,align]). Optional Render.TEXT_ALIGN_* (default center). |
| `DrawLine` | `Render.DrawLine(x1: number, y1: number, x2: number, y2: number, color: Color, thickness: number)` | safe |  |
| `Line` | `Render.Line(x1: number, y1: number, x2: number, y2: number, color: Color, thickness: number)` | safe | Also accepts (p1:Vec2, p2:Vec2, color[, thickness]). |
| `DrawBox` | `Render.DrawBox(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe |  |
| `Rect` | `Render.Rect(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe | Alias of DrawBox. |
| `DrawFilledBox` | `Render.DrawFilledBox(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe |  |
| `FilledRect` | `Render.FilledRect(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe | Also accepts (p1:Vec2, p2:Vec2, color). |
| `FilledRectRounded` | `Render.FilledRectRounded(p1: Vec2, p2: Vec2, color: Color, rounding: number, corner_flags?: integer)` | safe | Rounded-corner filled rect. corner_flags is an ImDrawFlags_RoundCorners* mask (Render.CORNER_*); omitted/0 rounds all four corners. |
| `DrawFilledBoxRounded` | `Render.DrawFilledBoxRounded(p1: Vec2, p2: Vec2, color: Color, rounding: number, corner_flags?: integer)` | safe | Alias of FilledRectRounded. |
| `RectRounded` | `Render.RectRounded(p1: Vec2, p2: Vec2, color: Color, rounding: number, thickness?: number, corner_flags?: integer)` | safe | Rounded-corner rectangle OUTLINE (DrawBox/Rect have no rounding option). corner_flags is an ImDrawFlags_RoundCorners* mask (Render.CORNER_*); omitted/0 rounds all four corners. |
| `DrawBoxRounded` | `Render.DrawBoxRounded(p1: Vec2, p2: Vec2, color: Color, rounding: number, thickness?: number, corner_flags?: integer)` | safe | Alias of RectRounded. |
| `CORNER_TOP_LEFT` | `.CORNER_TOP_LEFT: integer` | safe | corner_flags bit — round the top-left corner. |
| `CORNER_TOP_RIGHT` | `.CORNER_TOP_RIGHT: integer` | safe | corner_flags bit — round the top-right corner. |
| `CORNER_BOTTOM_LEFT` | `.CORNER_BOTTOM_LEFT: integer` | safe | corner_flags bit — round the bottom-left corner. |
| `CORNER_BOTTOM_RIGHT` | `.CORNER_BOTTOM_RIGHT: integer` | safe | corner_flags bit — round the bottom-right corner. |
| `CORNER_TOP` | `.CORNER_TOP: integer` | safe | corner_flags bit — round both top corners. |
| `CORNER_BOTTOM` | `.CORNER_BOTTOM: integer` | safe | corner_flags bit — round both bottom corners. |
| `CORNER_LEFT` | `.CORNER_LEFT: integer` | safe | corner_flags bit — round both left corners. |
| `CORNER_RIGHT` | `.CORNER_RIGHT: integer` | safe | corner_flags bit — round both right corners. |
| `CORNER_ALL` | `.CORNER_ALL: integer` | safe | corner_flags value — round all four corners (the default when corner_flags is omitted). |
| `CORNER_NONE` | `.CORNER_NONE: integer` | safe | corner_flags value — square corners (rounding has no visible effect). |
| `DrawCircle` | `Render.DrawCircle(x: number, y: number, radius: number, color: Color)` | safe |  |
| `Circle` | `Render.Circle(x: number, y: number, radius: number, color: Color)` | safe | Also accepts (center:Vec2, radius, color). See Render.CircleArc for rings/arcs with thickness. |
| `DrawFilledCircle` | `Render.DrawFilledCircle(x: number, y: number, radius: number, color: Color)` | safe |  |
| `FilledCircle` | `Render.FilledCircle(x: number, y: number, radius: number, color: Color)` | safe | Alias of DrawFilledCircle. |
| `DrawCircle3D` | `Render.DrawCircle3D(center: Vector3, radius: number, color: Color)` | safe |  |
| `DrawLine3D` | `Render.DrawLine3D(start: Vector3, finish: Vector3, color: Color, thickness: number)` | safe |  |
| `GetScreenSize` | `Render.GetScreenSize() -> table` | safe | Returns { width, height }. |
| `ScreenSize` | `Render.ScreenSize() -> table` | safe | Returns { width, height }. |
| `GetScreenCenter` | `Render.GetScreenCenter() -> table` | safe | Returns { x, y }. |
| `GetFPS` | `Render.GetFPS() -> number` | safe | Rendered frames per second: ImGui's average over the measured frame times, published once per frame. 0 before the first frame; reading it changes nothing. |
| `GetFrameTime` | `Render.GetFrameTime() -> number` | safe | Seconds per rendered frame, 1 / GetFPS (0 before the first frame). |
| `GetDeltaTime` | `Render.GetDeltaTime() -> number` | safe | The engine tick interval (about 1/64 s), not the frame time: use GetFrameTime for that. |
| `PresentCount` | `Render.PresentCount() -> integer` | safe | Frames the overlay has rendered since injection. |
| `TextCentered` | `Render.TextCentered(text: string, x: number, y: number, color: Color)` | safe |  |
| `TextSize` | `Render.TextSize(font: integer, size: number, text: string) -> table` | safe | Returns {x,y}; also accepts (text) and (font,text). When a font/size is given it measures with the exact FW1 face Render.Text draws with (real metrics at that size). |
| `LoadFont` | `Render.LoadFont(name: string, size?: integer, weight?: integer) -> integer` | safe | Size-INDEPENDENT font handle: `name` is a real system-font family (resolved via DirectWrite; empty/"Verdana" = the embedded default), `weight` a real DWRITE_FONT_WEIGHT (Render.FONT_WEIGHT_*). The per-call `size` in Render.Text/TextSize is honored (glyph atlas built per size); the `size` here is only the default when a draw call omits one. |
| `LoadFontFile` | `Render.LoadFontFile(path: string, size?: integer, weight?: integer) -> integer` | safe | Load a custom .ttf/.otf (absolute path) into the process-private font set and return a size-independent font handle bound to its family. 0 on failure (open / parse / register). Behaves like a Render.LoadFont handle (honors per-call size). |
| `FontMetrics` | `Render.FontMetrics(font: integer, size?: number) -> table` | safe | Returns { ascent, descent, line_height } measured from the same FW1 face Render.Text draws with, at `size` (or the handle's default size). |
| `ShowVisualsEnabled` | `Render.ShowVisualsEnabled() -> boolean` | safe | The 'lua/show_visuals' (Heroes page 'Show visuals') toggle. Gates ONLY the hero-engine's own visuals — custom/feature scripts always draw. Query it to mirror the hero-visual state. |
| `FONT_WEIGHT_REGULAR` | `.FONT_WEIGHT_REGULAR: integer` | safe | Render.LoadFont weight value (400) — real, distinct Verdana Regular face. |
| `FONT_WEIGHT_MEDIUM` | `.FONT_WEIGHT_MEDIUM: integer` | safe | Render.LoadFont weight value (500) — NO real Verdana Medium face exists; DirectWrite substitutes the nearest available weight (observed: Regular). |
| `FONT_WEIGHT_BOLD` | `.FONT_WEIGHT_BOLD: integer` | safe | Render.LoadFont weight value (700) — real, distinct Verdana Bold face; also the default when weight is omitted. |
| `TEXT_ALIGN_LEFT` | `.TEXT_ALIGN_LEFT: integer` | safe | Text horizontal alignment (anchor at left). Optional trailing `align` arg on Render.Text/DrawText/TextFont. |
| `TEXT_ALIGN_CENTER` | `.TEXT_ALIGN_CENTER: integer` | safe | Text horizontal alignment (anchor at center) — the historical default. |
| `TEXT_ALIGN_RIGHT` | `.TEXT_ALIGN_RIGHT: integer` | safe | Text horizontal alignment (anchor at right). |
| `TEXT_ALIGN_TOP` | `.TEXT_ALIGN_TOP: integer` | safe | Text vertical alignment (anchor at top). |
| `TEXT_ALIGN_VCENTER` | `.TEXT_ALIGN_VCENTER: integer` | safe | Text vertical alignment (anchor at vertical center). |
| `TEXT_ALIGN_BOTTOM` | `.TEXT_ALIGN_BOTTOM: integer` | safe | Text vertical alignment (anchor at bottom). OR a horizontal + vertical flag. |
| `TextFont` | `Render.TextFont(fontHandle: integer, x: number, y: number, text: string, color: Color, align?: integer)` | safe | Draw with a LoadFont/LoadFontFile handle; optional Render.TEXT_ALIGN_* (default center). |
| `FilledTriangle` | `Render.FilledTriangle(p1: Vec2, p2: Vec2, p3: Vec2, color: Color)` | safe | Filled triangle through the native deferred pipeline. |
| `Triangle` | `Render.Triangle(p1: Vec2, p2: Vec2, p3: Vec2, color: Color)` | safe | Alias of FilledTriangle. |
| `CircleArc` | `Render.CircleArc(center: Vec2, radius: number, color: Color, thickness?: number, start_deg?: number, frac?: number)` | safe | Arc / ring with real stroke width (cooldown rings). frac in (0,1] is the swept fraction (1 = full ring); start_deg is the clockwise start angle (0 = 3 o'clock). |
| `WorldToScreen` | `Render.WorldToScreen(world: Vector3) -> table` | safe | Returns { x, y, visible }. |
| `LoadImage` | `Render.LoadImage(path: string, flags?: integer) -> integer` | safe | Texture handle from a .vtex_c (0 on miss). Crash-safe for ANY input (decode is SEH-guarded); .vsvg_c/.svg are rasterized via the SVG path. |
| `Image` | `Render.Image(handle: integer, pos: Vec2, size?: Vec2, color?: Color, uv1?: any, uv2?: any, uv3?: any, uv4?: any, flags?: integer, rounding?: number)` | safe | Draw an image handle. Optional trailing `rounding` rounds the corners (round avatars/icons). |
| `ImageSize` | `ImageSize` | safe |  |
| `ImageCentered` | `ImageCentered` | safe |  |
| `FindOrCreateRT` | `Render.FindOrCreateRT(name: string, w: number, h: number) -> integer` | safe | Stable render-target handle per name. |
| `RenderToRT` | `Render.RenderToRT(rt: integer, fn: function)` | safe | Store a draw closure for the RT. |
| `DrawRT` | `Render.DrawRT(rt: integer, pos?: Vec2, size?: Vec2)` | safe | Re-invoke the RT's stored closure as fn(pos,size). |
| `PolygonFilled` | `PolygonFilled` | safe |  |
| `Polyline` | `Polyline` | safe |  |
| `Shadow` | `Render.Shadow(p1: Vec2, p2: Vec2, color: Color, size?: number, rounding?: number)` | safe | Soft drop-shadow behind a rect. |
| `ShadowCircle` | `Render.ShadowCircle(center: Vec2, radius: number, color: Color, size?: number)` | safe | Soft drop-shadow behind a circle. |
| `Gradient` | `Render.Gradient(p1: Vec2, p2: Vec2, c_tl: Color, c_tr: Color, c_bl: Color, c_br: Color, rounding?: number)` | safe | Four-corner gradient-filled rect. `rounding` is honored (rounded-rect fan with per-vertex bilinear corner colors); 0/omitted = square corners. |
| `CircleGradient` | `Render.CircleGradient(center: Vec2, radius: number, inner: Color, outer: Color)` | safe | Radial inner-to-outer gradient circle. |
| `OutlineGradient` | `Render.OutlineGradient(p1: Vec2, p2: Vec2, c_top: Color, c_bottom: Color, thickness?: number)` | safe | Top-to-bottom gradient rect outline. |
| `Blur` | `Render.Blur(p1: Vec2, p2: Vec2, strength?: number, alpha?: number, rounding?: number)` | safe | Blur the backbuffer under a rect. |
| `PushClip` | `Render.PushClip(p1: Vec2, p2: Vec2, intersect?: boolean)` | safe | Push a clip rectangle. |
| `PopClip` | `Render.PopClip()` | safe | Pop the last clip rectangle. |
| `GetHeroIcon` | `Render.GetHeroIcon(heroId: integer) -> integer` | safe | Hero portrait icon texture handle for an EHeroID_t (0 until icons loaded). |
| `GetAbilityIcon` | `Render.GetAbilityIcon(heroId: integer, slot: integer) -> integer` | safe | Ability icon texture handle (hero EHeroID_t + ability slot 0..3). |
| `GetItemIcon` | `Render.GetItemIcon(itemId: integer) -> integer` | safe | Item shop-icon texture handle. |
| `LoadImageFromMemory` | `Render.LoadImageFromMemory(bytes: string, expected_w?: integer, expected_h?: integer) -> integer` | safe | Decode raw PNG bytes to a texture handle; memoized by content. |
| `LoadGameImage` | `Render.LoadGameImage(path: string) -> integer` | safe | Load a compiled panorama vtex_c via the game UI image resource manager to a texture handle. |
| `CompileShader` | `Render.CompileShader(pixelSource: string, vertexSource?: string) -> integer, string\|nil` | safe | Compile HLSL into a shader handle (ps_5_0, plus vs_5_0 if vertexSource is given). Returns handle 0 and a compiler-error string on failure, or handle>=1 and nil on success. The pixel entry main receives (pos:SV_POSITION, col:COLOR0, uv:TEXCOORD0) and returns SV_TARGET; declaring cbuffer members float2 iResolution, float2 iMouse, float iTime, float iTimeDelta, float iFrame auto-fills them each draw. |
| `FreeShader` | `Render.FreeShader(handle: integer) -> boolean` | safe | Release a compiled shader and its GPU resources. |
| `SetShaderFloat` | `Render.SetShaderFloat(handle: integer, name: string, x: number) -> boolean` | safe | Set a named float uniform on the shader; false if no such uniform exists. |
| `SetShaderFloat2` | `Render.SetShaderFloat2(handle: integer, name: string, x: number, y: number) -> boolean` | safe | Set a named float2 uniform on the shader; false if no such uniform exists. |
| `SetShaderFloat3` | `Render.SetShaderFloat3(handle: integer, name: string, x: number, y: number, z: number) -> boolean` | safe | Set a named float3 uniform on the shader; false if no such uniform exists. |
| `SetShaderFloat4` | `Render.SetShaderFloat4(handle: integer, name: string, x: number, y: number, z: number, w: number) -> boolean` | safe | Set a named float4 uniform on the shader; false if no such uniform exists. |
| `SetShaderTexture` | `Render.SetShaderTexture(handle: integer, slot: integer, textureHandle?: integer) -> boolean` | safe | Bind a texture handle (from LoadImage/LoadGameImage/icons) to a shader sampler slot: 0 = primary quad texture (t0), 1..7 = extra inputs (t1..t7). Omit/0 clears the slot. |
| `DrawShaded` | `Render.DrawShaded(handle: integer, x: number, y: number, w: number, h: number, color?: Color) -> boolean` | safe | Paint a w x h quad at (x,y) through the compiled shader into the active draw list; uv spans 0..1 across the quad and color tints the vertices. |
| `LoadSvg` | `Render.LoadSvg(path: string, size?: number\|Vec2) -> integer` | safe | Image handle from a game SVG (.vsvg_c / .svg) rasterised at `size` (a number for a square or a Vec2; default 128 x 128, aspect-fit). 0 on failure. Cached per path and size. |
| `LoadSvgString` | `Render.LoadSvgString(svg: string, size?: number\|Vec2) -> integer` | safe | Image handle from SVG markup. Without a size the image keeps its own size as its draw size and is rasterised at a higher scale so it stays sharp when drawn larger. 0 on failure. |
| `LoadMaskedImage` | `Render.LoadMaskedImage(mask_path: string, image_path: string) -> integer` | safe | Two compiled panorama images (.vtex_c): the image stretched over the mask and cut to its shape (the mask's alpha, or its brightness when the mask is opaque everywhere). The result has the mask's size. 0 on failure. |
| `LoadGameFont` | `Render.LoadGameFont(name: string, size?: integer, weight?: integer) -> integer` | safe | Font handle for one of the game's own typefaces by family name ("Radiance", "Retail Demo", "VALVE Oracle"; case, spaces, dashes and underscores ignored), installed from the game folder on first use. size defaults to 9, weight to regular. 0 when the game ships no such family. |
| `SetGlobalAlpha` | `Render.SetGlobalAlpha(alpha: number)` | safe | Fades everything drawn by Render.* until ResetGlobalAlpha (or the next SetGlobalAlpha) by alpha in [0, 1]. Render thread inside a draw callback; a no-op elsewhere. A window left open past the frame is dropped. |
| `ResetGlobalAlpha` | `Render.ResetGlobalAlpha()` | safe | Closes the SetGlobalAlpha window. |

### Menu

`table` · tier `safe` — Menu tree entry points (Create/Find/Tab) + style/state.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Create` | `Menu.Create(a: string, b?: string, c?: string, d?: string, e?: string) -> MenuNode` | safe | Build/find a menu path; a hero script's path is auto-re-rooted under Heroes/Hero List/<hero>. |
| `Find` | `Menu.Find(a: string, b?: string, c?: string, d?: string, e?: string, f?: string) -> MenuNode\|nil` | safe |  |
| `Tab` | `Menu.Tab(name: string) -> MenuNode` | safe |  |
| `Style` | `Menu.Style(name?: string) -> Color\|table` | safe | Themed color for a palette name (primary/text/background/shadow + aliases); no arg returns the full theme table. |
| `Opened` | `Menu.Opened() -> boolean` | safe |  |
| `Panel` | `Menu.Panel(row: MenuNode, opts: table) -> MenuPanel\|nil` | safe | A HUD panel placement owned by one of the script's Switch or Combo rows, kept like the native overlays' (a screen cell + offset, or a dragged position; own or HUD scale and opacity) and edited from the row's "...". opts = { id (1-31 of a-z 0-9 _), cell (0..8, top-left to bottom-right row by row; default 4) }. nil after a console error. |

### Aim

`table` · tier `safe` — Aim helpers (psilent + world-to-screen).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `AimAtPlayer` | `Aim.AimAtPlayer(controller: any, eyePos: Vector3, viewDir: Vector3, target: PlayerTarget) -> AimResult` | safe | Projectile aim solution vs a player-bone target. |
| `AimAtSoul` | `Aim.AimAtSoul(controller: any, eyePos: Vector3, viewDir: Vector3, target: SoulTarget) -> AimResult` | safe | Projectile aim solution vs a soul orb. |
| `AimAtDeployable` | `Aim.AimAtDeployable(controller: any, eyePos: Vector3, viewDir: Vector3, target: DeployableTarget) -> AimResult` | safe | Projectile aim solution vs a deployable/area target. |
| `Solve` | `Aim.Solve(input: AimInput) -> AimResult` | safe | Solve a projectile aim from a fully-specified AimInput. |
| `SolveAtPoint` | `Aim.SolveAtPoint(input: AimInput) -> AimResult` | safe | Solve a projectile aim from an AimInput at its target point. |
| `GetBulletPhysics` | `Aim.GetBulletPhysics(controller: any) -> WeaponBulletData` | safe | Local weapon bullet physics (speed/gravity/radius). |
| `InvalidateBulletCache` | `Aim.InvalidateBulletCache() -> nil` | safe | Invalidate the cached bullet physics so the next call recomputes. |
| `FOVToPixelRadius` | `Aim.FOVToPixelRadius(fovDegrees: number) -> number` | safe | Convert an aim cone's radius in degrees (the unit of is_pos_within_fov and every aim FOV) to a screen-pixel radius. A cone of 89.5 degrees or more is the whole view and returns half the screen diagonal; 0 or less returns 0. |
| `PixelRadiusToFOV` | `Aim.PixelRadiusToFOV(pixelRadius: number) -> number` | safe | Returns the cone radius in degrees for a pixel radius (the inverse of FOVToPixelRadius); 0 for a pixel radius of 0 or less. |
| `status` | `.status: table` | safe | aim.status / Aim.status: what cmd:aim and HERO_LIB.aim return. PENDING 0 (under way, not on target yet: the PSilent hold settles, the reaction wait, a failed hit-chance roll), AIMING 1 (the view is turning onto the target), READY 2 (the shot can go out on this command), BUSY 3 (the action gate holds, or another aim owns the bus or the view this tick), INVALID 4 (nothing to aim at, refused by Safety or the request's own cone, out of reach), BLOCKED 5 (the shot cannot reach its trace point, or no camera spot within reach sees the target). |
| `type` | `.type: table` | safe | aim.type / Aim.type bits for cmd:aim's aim_type (OR them to allow more than one): DEFAULT 1 (the screen-space aimbot turns the view), SILENT 2 and MAGIC_BULLETS 4 (both on the PSilent bus: the silent shot always moves the camera it leaves from along the unchanged view, so there is no angle-only form). |

### callback

`table` · tier `safe` — Event channels. callback.on_<name> is a channel handle (:set / :add, see CallbackHandle); callback.add / once / throttled take the channel name. Every fire of a channel, whether from the game, a bridge event or callback.fire, runs its handlers in registration order and honours pause_script, set_channel_throttle, disable, once, throttled and the `when` gate. The menu, cursor and typing edges are recorded where they happen and delivered on the game thread at the next frame stage (in menus too, not during a map change); a state that flips back before then fires nothing.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_pre_createmove` | `on_pre_createmove` | safe |  |
| `on_createmove` | `on_createmove` | safe |  |
| `on_frame` | `on_frame` | safe |  |
| `on_draw` | `on_draw` | safe |  |
| `on_add_modifier` | `on_add_modifier` | safe | Channel handle; handlers get (mod, holder_handle, modifier, target, caster) (see the on_add_modifier event). NEW: an optional filter, :set(fn, { modifiers = { name, ... } }) (also :add and callback.add): the handler fires only for those modifier names (case-insensitive), checked natively before Lua runs; without it the handler gets every event. |
| `on_remove_modifier` | `on_remove_modifier` | safe | Channel handle; handlers get (mod, holder_handle, modifier_name, target, caster) (see the on_remove_modifier event). NEW: an optional filter, :set(fn, { modifiers = { name, ... } }) (also :add and callback.add): the handler fires only for those modifier names (case-insensitive), checked natively before Lua runs; without it the handler gets every event. |
| `on_bullet_create` | `on_bullet_create` | safe |  |
| `on_particle_create` | `on_particle_create` | safe |  |
| `on_particle_update` | `on_particle_update` | safe |  |
| `on_particle_destroy` | `on_particle_destroy` | safe |  |
| `on_take_damage` | `on_take_damage` | safe |  |
| `on_game_event` | `on_game_event` | safe |  |
| `on_key` | `callback.on_key(code: integer, isDown: boolean) -> boolean\|nil` | safe | Fires for keyboard AND mouse buttons: mouse buttons report via the standard VK_* code (Keys.MOUSE1..MOUSE5 = VK_LBUTTON/VK_RBUTTON/VK_MBUTTON/VK_XBUTTON1/VK_XBUTTON2) with isDown=true/false on the button down/up transition. Return a truthy value to CLAIM the key/button (blocks it from the game and the menu/panic handlers). |
| `on_scroll` | `callback.on_scroll(delta: integer, horizontal: boolean) -> boolean\|nil` | safe | Mouse-wheel notch (WM_MOUSEWHEEL/WM_MOUSEHWHEEL). delta is signed WHEEL_DELTA(120) units; horizontal is true for the tilt-wheel/shift-scroll axis. Return a truthy value to CLAIM the wheel tick (mirrors on_key's block semantics) — e.g. a script's scroll region owning the notch instead of the underlying UI. |
| `on_entity_create` | `callback.on_entity_create(entity: Entity, idx: integer)` | safe |  |
| `on_entity_destroy` | `callback.on_entity_destroy(entity: Entity\|nil, idx: integer)` | safe |  |
| `on_sound` | `on_sound` | safe |  |
| `on_scripts_loaded` | `on_scripts_loaded` | safe |  |
| `on_map_load_start` | `on_map_load_start` | safe | Map load begins (loading screen up, before local pawn spawn). |
| `on_map_load_full` | `on_map_load_full` | safe | Local pawn spawned into a live match (map fully loaded). |
| `add` | `callback.add(channel: string, handler: function, opts: {when:'any'\|'menu_open'\|'menu_closed'\|'ingame'\|'typing'\|'not_typing'\|'cursor_visible'\|'cursor_hidden'}?) -> integer` | safe | Register a handler on `channel`. Optional 3rd arg is an options table (or a bare when-token string) that gates the fire against the sampled input state -- 'menu_open' fires only while the menu is up, 'ingame' fires only while the menu is closed AND the cursor is locked, 'typing' only while a text field has keyboard focus, etc. Returns the callback id (0 on failure). |
| `once` | `callback.once(channel: string, handler: function, opts?: table\|string) -> integer` | safe | callback.add for one call: the handler is removed after the first fire that calls it. |
| `throttled` | `callback.throttled(channel: string, ms: integer, handler: function, opts?: table\|string) -> integer` | safe | callback.add with a per-handler limit: a fire within ms (0..60000) of this handler's last successful call skips it. |
| `dispatch` | `callback.dispatch(channel: string, ...: any)` | safe | Fire `channel` now, on this thread: every script's handlers on it run in registration order with the remaining arguments, before this call returns. A handler's error is reported for that handler and does not reach the caller. The game's own fire path, so pause, the throttles, disable, once and `when` apply. |
| `fire` | `callback.fire(channel: string, ...: any)` | safe | Same function as dispatch. |
| `publish` | `callback.publish(channel: string, ...: any)` | safe | Same function as dispatch. |
| `dispatch_many` | `callback.dispatch_many(channels: string[], ...: any)` | safe | callback.dispatch on each channel named in the table, with the same arguments. |
| `fanout` | `callback.fanout(channels: string[], ...: any)` | safe | Same function as dispatch_many. |
| `wildcard_dispatch` | `callback.wildcard_dispatch(pattern: string, ...: any)` | safe | callback.dispatch on every registered channel the pattern matches: "prefix*" matches by prefix, a pattern without a trailing * only that exact name. An empty pattern fires nothing. |
| `dispatch_matching` | `callback.dispatch_matching(pattern: string, ...: any)` | safe | Same function as wildcard_dispatch. |
| `context` | `callback.context() -> table` | safe | The dispatch running on this thread: { script, channel, depth, seq, global_seq }. script and channel name the handler being called ("(none)" outside a dispatch); depth counts the dispatches nested on this thread (0 outside one); seq counts the dispatch contexts entered and global_seq the channel fires, both since boot and on every thread. |
| `pause_script` | `callback.pause_script(script: string) -> boolean` | safe | Stop calling the named script's handlers on every channel, game and bridge events included, until resume_script. Returns true. |
| `resume_script` | `callback.resume_script(script: string) -> boolean` | safe | Undo pause_script. Returns true. |
| `is_script_paused` | `callback.is_script_paused(script: string) -> boolean` | safe |  |
| `list_paused` | `callback.list_paused() -> string[]` | safe | Names of the paused scripts. |
| `set_channel_throttle` | `callback.set_channel_throttle(channel: string, min_ms: integer) -> boolean` | safe | Drop a whole fire of `channel` (every handler) that comes within min_ms of the last fire that ran, whatever its source: the game, a bridge event or callback.dispatch. Returns true. |
| `get_channel_throttle` | `callback.get_channel_throttle(channel: string) -> integer` | safe | The channel's min_ms; 0 when none is set. |
| `clear_channel_throttle` | `callback.clear_channel_throttle(channel: string) -> boolean` | safe | Remove the channel's throttle. Returns true. |
| `on_menu_open` | `callback.on_menu_open()` | safe | Edge event, delivered on the game thread: the menu opened. |
| `on_menu_close` | `callback.on_menu_close()` | safe | Edge event, delivered on the game thread: the menu closed. |
| `on_cursor_shown` | `callback.on_cursor_shown()` | safe | Edge event, delivered on the game thread: the cursor became visible (the menu opened, a modal grabbed input, or the game released the mouse). |
| `on_cursor_hidden` | `callback.on_cursor_hidden()` | safe | Edge event, delivered on the game thread: the cursor became hidden (the game captured the mouse again). |
| `on_typing_start` | `callback.on_typing_start()` | safe | Edge event, delivered on the game thread: typing started (Input.is_typing turned true: the chat or console took text, or a text field got keyboard focus). |
| `on_typing_end` | `callback.on_typing_end()` | safe | Edge event, delivered on the game thread: typing ended (Input.is_typing turned false). |
| `on_hero_killed` | `callback.on_hero_killed(killer: integer, victim: integer, ability_id: integer, detail: table)` | safe | A hero died: once per kill, from the game's HeroKilled user message. killer and victim are entity indices (-1 when the message leaves them unset); ability_id is the killing ability's id from the message; detail = { inflictor, scorer, assisters = { index, ... } }, entity indices too. |
| `on_local_pawn_spawn` | `callback.on_local_pawn_spawn(pawn: lightuserdata)` | safe | Game thread, on the CreateMove tick that first sees a local pawn. pawn is a raw handle for entity_list / HERO_LIB functions. |
| `on_local_pawn_death` | `callback.on_local_pawn_death(pawn: lightuserdata)` | safe | Game thread, on the CreateMove tick that no longer sees the local pawn. pawn is the one that went away: compare it, do not read through it. |
| `on_local_pawn_change` | `callback.on_local_pawn_change(pawn: lightuserdata, previous: lightuserdata)` | safe | Game thread: the local pawn became a different entity between two CreateMove ticks. |
| `on_pre_render` | `callback.on_pre_render()` | safe | Game thread, at most once per game tick while frames are presented: on_pre_render, then the on_frame functions scripts define, then on_present, then on_post_render. Nothing is drawn here: draw in on_draw. |
| `on_present` | `callback.on_present()` | safe | See on_pre_render. |
| `on_post_render` | `callback.on_post_render()` | safe | See on_pre_render. |
| `on_load` | `callback.on_load(script: string)` | safe | A script finished loading, after its own on_load. Every script's handlers hear every script, the loading script included. |
| `on_unload` | `callback.on_unload(script: string)` | safe | A script is unloading, after its own on_unload and before its handlers are removed; also for every script at shutdown. |
| `on_reload` | `callback.on_reload(script: string)` | safe | A script was reloaded from disk, after its load event. |
| `on_add_entity` | `on_add_entity` | safe | Alias of on_entity_create (same channel). |
| `on_remove_entity` | `on_remove_entity` | safe | Alias of on_entity_destroy (same channel). |
| `on_particle_update_transform` | `on_particle_update_transform` | safe | Alias of on_particle_update (same channel). |
| `on_pre_frame` | `on_pre_frame` | safe | Per-frame game-thread work begins (brackets with on_post_frame). |
| `on_post_frame` | `on_post_frame` | safe | Per-frame game-thread work ends. |
| `on_pre_framestage` | `callback.on_pre_framestage(stage: integer)` | safe | Frame stage begins; stage is a FrameStage enum value (only NET_UPDATE_POSTDATAUPDATE_END fires this build). |
| `on_post_framestage` | `callback.on_post_framestage(stage: integer)` | safe | Frame stage ends; stage is a FrameStage enum value. |
| `on_modifier_added` | `on_modifier_added` | safe | Alias of on_add_modifier (same per-script slot); handlers get (mod, holder_handle, modifier, target, caster). |
| `on_modifier_removed` | `on_modifier_removed` | safe | Alias of on_remove_modifier (same per-script slot); handlers get (mod, holder_handle, modifier_name, target, caster). |
| `on_fire_bullets` | `on_fire_bullets` | safe | Alias of on_bullet_create (same per-script slot). |
| `on_key_event` | `callback.on_key_event(code: integer, isDown: boolean) -> boolean\|nil` | safe | Alias of on_key (same per-script slot). Also reports mouse buttons via the standard VK_* code (see on_key) — a truthy return claims the button press exactly like it claims a key. |

### ImGui

`table` · tier `safe` — Immediate-mode GUI primitives.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Begin` | `Begin` | safe | Opens a window scope. A 65th nested Begin is refused (returns false) instead of overflowing the scope stack. |
| `End` | `End` | safe |  |
| `Window` | `Window` | safe |  |
| `CaptureInput` | `ImGui.CaptureInput()` | safe | Gives your windows the mouse and keyboard for this frame, the way the open menu has them: the cursor shows, mouse look pauses and the game stops receiving input. Call it from on_draw on every frame your interactive window is open (e.g. while your own toggle key has it shown); stop calling it and the game gets its input back on the next frame, so closing the window, unloading the script or a script error all release it. Never call it for a HUD or overlay window. Takes effect only while the game window has focus. |
| `SetNextWindowSize` | `SetNextWindowSize` | safe |  |
| `SetNextWindowPos` | `SetNextWindowPos` | safe |  |
| `SetNextItemWidth` | `SetNextItemWidth` | safe |  |
| `Text` | `Text` | safe |  |
| `TextWrapped` | `TextWrapped` | safe |  |
| `TextDisabled` | `TextDisabled` | safe |  |
| `TextColored` | `TextColored` | safe |  |
| `BulletText` | `BulletText` | safe |  |
| `LabelText` | `LabelText` | safe |  |
| `Separator` | `Separator` | safe |  |
| `SeparatorText` | `SeparatorText` | safe |  |
| `Spacing` | `Spacing` | safe |  |
| `NewLine` | `NewLine` | safe |  |
| `Bullet` | `Bullet` | safe |  |
| `Indent` | `Indent` | safe |  |
| `Unindent` | `Unindent` | safe |  |
| `SameLine` | `SameLine` | safe |  |
| `Dummy` | `Dummy` | safe |  |
| `Button` | `Button` | safe |  |
| `SmallButton` | `SmallButton` | safe |  |
| `Checkbox` | `Checkbox` | safe |  |
| `RadioButton` | `RadioButton` | safe |  |
| `SliderFloat` | `SliderFloat` | safe |  |
| `SliderInt` | `SliderInt` | safe |  |
| `DragFloat` | `DragFloat` | safe |  |
| `DragInt` | `DragInt` | safe |  |
| `InputInt` | `InputInt` | safe |  |
| `InputFloat` | `InputFloat` | safe |  |
| `InputText` | `InputText` | safe |  |
| `Combo` | `Combo` | safe |  |
| `ColorEdit` | `ColorEdit` | safe |  |
| `CollapsingHeader` | `CollapsingHeader` | safe |  |
| `ProgressBar` | `ProgressBar` | safe |  |
| `IsItemHovered` | `IsItemHovered` | safe |  |
| `IsItemClicked` | `IsItemClicked` | safe |  |
| `SetTooltip` | `SetTooltip` | safe |  |
| `GetContentRegionAvail` | `GetContentRegionAvail` | safe |  |

### Input

`table` · tier `safe` — Keyboard / mouse input queries.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `IsKeyDown` | `Input.IsKeyDown(vk: integer) -> boolean` | safe |  |
| `is_down` | `is_down` | safe |  |
| `is_key_down` | `is_key_down` | safe |  |
| `is_pressed` | `Input.is_pressed(vk: integer) -> boolean` | safe | True once when the key goes down. False while typing (see is_typing); is_down is unaffected. |
| `cursor_in_bounds` | `cursor_in_bounds` | safe |  |
| `GetMousePos` | `Input.GetMousePos() -> table` | safe | Returns { x, y }. |
| `get_cursor_pos` | `get_cursor_pos` | safe |  |
| `GetMouseDelta` | `GetMouseDelta` | safe |  |
| `mouse_wheel` | `Input.mouse_wheel() -> integer` | safe | Vertical mouse-wheel delta accumulated since the last call: 120 per notch (WHEEL_DELTA); touchpads give smaller values. +away from user / -toward. Consumes the accumulator; every read in one frame returns the same value, so a per-frame poll never double-counts a notch. |
| `mouse_wheel_h` | `Input.mouse_wheel_h() -> integer` | safe | Horizontal mouse-wheel delta since the last call (shift-scroll / tilt-wheel, WM_MOUSEHWHEEL): 120 per notch (WHEEL_DELTA); touchpads give smaller values. Same consume semantics as mouse_wheel(). |
| `is_menu_open` | `Input.is_menu_open() -> boolean` | safe | True while the Avalanche menu is open (uses fw::menu::open_intent). |
| `IsMenuOpen` | `Input.IsMenuOpen() -> boolean` | safe |  |
| `menu_open` | `Input.menu_open() -> boolean` | safe |  |
| `is_cursor_visible` | `Input.is_cursor_visible() -> boolean` | safe | True while the mouse cursor is being drawn (menu, modal, or game-side unlock). Backed by ImGuiIO::MouseDrawCursor at frame time. |
| `IsCursorVisible` | `Input.IsCursorVisible() -> boolean` | safe |  |
| `cursor_visible` | `Input.cursor_visible() -> boolean` | safe |  |
| `is_ingame` | `Input.is_ingame() -> boolean` | safe | True when the menu is closed AND the cursor is locked -- i.e. the game has capture and the player is controlling their hero. |
| `IsInGame` | `Input.IsInGame() -> boolean` | safe |  |
| `in_game` | `Input.in_game() -> boolean` | safe |  |
| `is_typing` | `Input.is_typing() -> boolean` | safe | True while someone is typing: the game's chat or console takes text, or a text field of the menu or a Lua window has keyboard focus. Sampled once per rendered frame. Menu navigation alone does not count. |
| `IsTyping` | `Input.IsTyping() -> boolean` | safe | Same function as is_typing. |
| `typing` | `Input.typing() -> boolean` | safe | Same function as is_typing. |

### Keys

`table` · tier `safe` — Key-code constants: the Windows VK of every key a bind can use, left and right modifiers apart. enums.VKey is the same table.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `MOUSE1` | `.MOUSE1: integer` | safe |  |
| `MOUSE2` | `.MOUSE2: integer` | safe |  |
| `MOUSE3` | `.MOUSE3: integer` | safe |  |
| `MOUSE4` | `.MOUSE4: integer` | safe |  |
| `MOUSE5` | `.MOUSE5: integer` | safe |  |
| `SHIFT` | `.SHIFT: integer` | safe |  |
| `CTRL` | `.CTRL: integer` | safe |  |
| `ALT` | `.ALT: integer` | safe |  |
| `SPACE` | `.SPACE: integer` | safe |  |
| `TAB` | `.TAB: integer` | safe |  |
| `ENTER` | `.ENTER: integer` | safe |  |
| `ESC` | `.ESC: integer` | safe |  |
| `F1` | `.F1: integer` | safe |  |
| `F2` | `.F2: integer` | safe |  |
| `F3` | `.F3: integer` | safe |  |
| `F4` | `.F4: integer` | safe |  |
| `F5` | `.F5: integer` | safe |  |
| `F6` | `.F6: integer` | safe |  |
| `F7` | `.F7: integer` | safe |  |
| `F8` | `.F8: integer` | safe |  |
| `F9` | `.F9: integer` | safe |  |
| `F10` | `.F10: integer` | safe |  |
| `F11` | `.F11: integer` | safe |  |
| `F12` | `.F12: integer` | safe |  |
| `A` | `.A: integer` | safe |  |
| `B` | `.B: integer` | safe |  |
| `C` | `.C: integer` | safe |  |
| `D` | `.D: integer` | safe |  |
| `E` | `.E: integer` | safe |  |
| `F` | `.F: integer` | safe |  |
| `G` | `.G: integer` | safe |  |
| `H` | `.H: integer` | safe |  |
| `I` | `.I: integer` | safe |  |
| `J` | `.J: integer` | safe |  |
| `K` | `.K: integer` | safe |  |
| `L` | `.L: integer` | safe |  |
| `M` | `.M: integer` | safe |  |
| `N` | `.N: integer` | safe |  |
| `O` | `.O: integer` | safe |  |
| `P` | `.P: integer` | safe |  |
| `Q` | `.Q: integer` | safe |  |
| `R` | `.R: integer` | safe |  |
| `S` | `.S: integer` | safe |  |
| `T` | `.T: integer` | safe |  |
| `U` | `.U: integer` | safe |  |
| `V` | `.V: integer` | safe |  |
| `W` | `.W: integer` | safe |  |
| `X` | `.X: integer` | safe |  |
| `Y` | `.Y: integer` | safe |  |
| `Z` | `.Z: integer` | safe |  |
| `0` | `.0: integer` | safe |  |
| `1` | `.1: integer` | safe |  |
| `2` | `.2: integer` | safe |  |
| `3` | `.3: integer` | safe |  |
| `4` | `.4: integer` | safe |  |
| `5` | `.5: integer` | safe |  |
| `6` | `.6: integer` | safe |  |
| `7` | `.7: integer` | safe |  |
| `8` | `.8: integer` | safe |  |
| `9` | `.9: integer` | safe |  |
| `LSHIFT` | `.LSHIFT: integer` | safe | Left Shift. |
| `RSHIFT` | `.RSHIFT: integer` | safe | Right Shift. |
| `LCTRL` | `.LCTRL: integer` | safe | Left Ctrl. |
| `RCTRL` | `.RCTRL: integer` | safe | Right Ctrl. |
| `LALT` | `.LALT: integer` | safe | Left Alt. |
| `RALT` | `.RALT: integer` | safe | Right Alt (AltGr). |
| `LWIN` | `.LWIN: integer` | safe | Left Windows key. |
| `RWIN` | `.RWIN: integer` | safe | Right Windows key. |
| `APPS` | `.APPS: integer` | safe | Menu (application) key. |
| `BACKSPACE` | `.BACKSPACE: integer` | safe |  |
| `INSERT` | `.INSERT: integer` | safe |  |
| `DELETE` | `.DELETE: integer` | safe |  |
| `HOME` | `.HOME: integer` | safe |  |
| `END` | `.END: integer` | safe |  |
| `PAGEUP` | `.PAGEUP: integer` | safe |  |
| `PAGEDOWN` | `.PAGEDOWN: integer` | safe |  |
| `LEFT` | `.LEFT: integer` | safe | Left arrow. |
| `RIGHT` | `.RIGHT: integer` | safe | Right arrow. |
| `UP` | `.UP: integer` | safe | Up arrow. |
| `DOWN` | `.DOWN: integer` | safe | Down arrow. |
| `CAPSLOCK` | `.CAPSLOCK: integer` | safe |  |
| `SCROLLLOCK` | `.SCROLLLOCK: integer` | safe |  |
| `NUMLOCK` | `.NUMLOCK: integer` | safe |  |
| `PRINTSCREEN` | `.PRINTSCREEN: integer` | safe |  |
| `PAUSE` | `.PAUSE: integer` | safe |  |
| `NUM_DECIMAL` | `.NUM_DECIMAL: integer` | safe | Numpad decimal point. |
| `NUM_DIVIDE` | `.NUM_DIVIDE: integer` | safe | Numpad /. |
| `NUM_MULTIPLY` | `.NUM_MULTIPLY: integer` | safe | Numpad *. |
| `NUM_SUBTRACT` | `.NUM_SUBTRACT: integer` | safe | Numpad -. |
| `NUM_ADD` | `.NUM_ADD: integer` | safe | Numpad +. |
| `MINUS` | `.MINUS: integer` | safe | The minus key (US position). Its VK follows the keyboard layout. |
| `EQUAL` | `.EQUAL: integer` | safe | The equals key (US position). Its VK follows the keyboard layout. |
| `LBRACKET` | `.LBRACKET: integer` | safe | The left bracket key (US position). Its VK follows the keyboard layout. |
| `RBRACKET` | `.RBRACKET: integer` | safe | The right bracket key (US position). Its VK follows the keyboard layout. |
| `BACKSLASH` | `.BACKSLASH: integer` | safe | The backslash key (US position). Its VK follows the keyboard layout. |
| `SEMICOLON` | `.SEMICOLON: integer` | safe | The semicolon key (US position). Its VK follows the keyboard layout. |
| `APOSTROPHE` | `.APOSTROPHE: integer` | safe | The apostrophe key (US position). Its VK follows the keyboard layout. |
| `GRAVE` | `.GRAVE: integer` | safe | The grave accent (tilde) key (US position). Its VK follows the keyboard layout. |
| `COMMA` | `.COMMA: integer` | safe | The comma key (US position). Its VK follows the keyboard layout. |
| `PERIOD` | `.PERIOD: integer` | safe | The period key (US position). Its VK follows the keyboard layout. |
| `SLASH` | `.SLASH: integer` | safe | The slash key (US position). Its VK follows the keyboard layout. |
| `OEM102` | `.OEM102: integer` | safe | The ISO key between Left Shift and Z ("<>"). Its VK follows the keyboard layout. |
| `BROWSER_BACK` | `.BROWSER_BACK: integer` | safe | Browser Back key. |
| `BROWSER_FORWARD` | `.BROWSER_FORWARD: integer` | safe | Browser Forward key. |
| `NUM0` | `.NUM0: integer` | safe | Numpad 0. |
| `NUM1` | `.NUM1: integer` | safe | Numpad 1. |
| `NUM2` | `.NUM2: integer` | safe | Numpad 2. |
| `NUM3` | `.NUM3: integer` | safe | Numpad 3. |
| `NUM4` | `.NUM4: integer` | safe | Numpad 4. |
| `NUM5` | `.NUM5: integer` | safe | Numpad 5. |
| `NUM6` | `.NUM6: integer` | safe | Numpad 6. |
| `NUM7` | `.NUM7: integer` | safe | Numpad 7. |
| `NUM8` | `.NUM8: integer` | safe | Numpad 8. |
| `NUM9` | `.NUM9: integer` | safe | Numpad 9. |
| `F13` | `.F13: integer` | safe |  |
| `F14` | `.F14: integer` | safe |  |
| `F15` | `.F15: integer` | safe |  |
| `F16` | `.F16: integer` | safe |  |
| `F17` | `.F17: integer` | safe |  |
| `F18` | `.F18: integer` | safe |  |
| `F19` | `.F19: integer` | safe |  |
| `F20` | `.F20: integer` | safe |  |
| `F21` | `.F21: integer` | safe |  |
| `F22` | `.F22: integer` | safe |  |
| `F23` | `.F23: integer` | safe |  |
| `F24` | `.F24: integer` | safe |  |

### GlowMode

`table` · tier `safe` — Glow render-mode constants (set_glow mode).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Disabled` | `.Disabled: integer` | safe | 0 |
| `Outline` | `.Outline: integer` | safe | 1 |
| `Fill` | `.Fill: integer` | safe | 2 |
| `HP` | `.HP: integer` | safe | 3 |

### FrameStage

`table` · tier `safe` — Frame-stage constants (on_pre_framestage / on_post_framestage).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `UNDEFINED` | `.UNDEFINED: integer` | safe | -1 |
| `START` | `.START: integer` | safe | 0 |
| `NET_UPDATE_START` | `.NET_UPDATE_START: integer` | safe | 1 |
| `NET_UPDATE_POSTDATAUPDATE_START` | `.NET_UPDATE_POSTDATAUPDATE_START: integer` | safe | 2 |
| `NET_UPDATE_POSTDATAUPDATE_END` | `.NET_UPDATE_POSTDATAUPDATE_END: integer` | safe | 3 |
| `NET_UPDATE_END` | `.NET_UPDATE_END: integer` | safe | 4 |
| `RENDER_START` | `.RENDER_START: integer` | safe | 5 |
| `RENDER_END` | `.RENDER_END: integer` | safe | 6 |

### entity_list

`table` · tier `safe` — Entity enumeration (local pawn / enemies / allies / by class / radius). Reads the per-tick entity frame: values lag the live entities by up to one tick, and an entity spawned after the tick's build appears from the next tick.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `local_pawn` | `entity_list.local_pawn() -> PlayerPawn\|nil` | safe |  |
| `enemies` | `entity_list.enemies() -> PlayerPawn[]` | safe | Player pawns opposed to the local player (the frame's relation rule: the other team, or no playable team); empty without a local pawn. Tick snapshot. |
| `allies` | `entity_list.allies() -> PlayerPawn[]` | safe | Teammate pawns (their controller's team is the local team), the local pawn excluded. Tick snapshot. |
| `by_class_name` | `entity_list.by_class_name(class: string) -> table` | safe | Player pawns whose schema binding name equals class ("C_CitadelPlayerPawn" / "player": entity_list.players). Tick snapshot. |
| `by_class_name_any` | `entity_list.by_class_name_any(class: string) -> Entity[]` | safe | Like by_class_name but with NO player-pawn filter: returns generic Entity usertypes for ANY class match (NPCs / structures / projectiles). The ONLY entity_list path to the lane Guardian ("C_NPC_TrooperBoss") and other bosses — by_class_name hard-filters to player pawns, so it can never see one. Walks every record of the per-tick entity frame, unclassified ones included. |
| `local_controller` | `entity_list.local_controller() -> Entity\|nil` | safe | The local player's controller (av::ef::LocalController), or nil. |
| `players` | `entity_list.players() -> PlayerPawn[]` | safe | Every player hero-pawn (controller->hero-pawn walk + pawn bucket, deduped) — includes PRE-INIT players and controller-less dummies/bots. 1-indexed. |
| `heroes` | `entity_list.heroes() -> PlayerPawn[]` | safe | Identical to entity_list.players (same enumeration). |
| `by_index` | `entity_list.by_index(index: integer) -> PlayerPawn\|nil` | safe | Resolve a 0-based entity ENTRY index to a PlayerPawn through the tick's entity frame; nil if the slot holds no Citadel player pawn (or the pawn spawned after the build). |
| `get_all` | `entity_list.get_all() -> PlayerPawn[]` | safe | Every cached CITADEL_PLAYER_PAWN (pawn bucket only; capped 1024). Prefer entity_list.players for full coverage. |
| `get_all_entities` | `entity_list.get_all_entities() -> Entity[]` | safe | GENERIC walk over EVERY cached entity type as Entity usertypes (identity-checked; capped 4096). |
| `entity_by_index` | `entity_list.entity_by_index(index: integer) -> Entity\|nil` | safe | Resolve ANY 0-based entity index to a generic Entity through the tick's entity frame, or nil. |
| `by_handle` | `entity_list.by_handle(raw_handle: integer) -> Entity\|nil` | safe | Resolve a full 32-bit entity handle (entry index + serial bits, serial-validated) to a generic Entity usertype, or nil: the value PlayerPawn:get_handle(), Entity:get_handle(), Modifier:get_caster_handle() and callback.on_particle_create's `index` carry, so they round-trip. A negative integer is read as the same 32 bits. CHANGED: a handle whose serial sets bit 31 used to be rejected. It is NOT a bare entry index: for that use entity_by_index / get_index(). |
| `teammates` | `entity_list.teammates() -> PlayerPawn[]` | safe | Same as entity_list.allies. |
| `team_filter` | `.team_filter: table` | safe | Constant team hints: { enemy = 3, ally = 2, all = 0 } — Deadlock TEAM SLOTS, not 0/1/2 array indices. |
| `in_radius` | `entity_list.in_radius(center?: Entity\|Vector3, radius?: number) -> Entity[]` | safe | Entities within radius units (default 500) of center: an entity's origin, a Vector3 or {x, y, z} point, else the local pawn's origin; at most 128. Origins come from the tick snapshot (an unclassified entity reads its own). |
| `heroes_in_radius` | `entity_list.heroes_in_radius(center?: Entity\|Vector3, radius?: number) -> PlayerPawn[]` | safe | in_radius over player pawns. |
| `souls_in_radius` | `entity_list.souls_in_radius(center?: Entity\|Vector3, radius?: number) -> Entity[]` | safe | in_radius over designer names npc_orb* / citadel_orb*. |
| `troopers_in_radius` | `entity_list.troopers_in_radius(center?: Entity\|Vector3, radius?: number) -> Entity[]` | safe | in_radius over designer names npc_trooper*. |
| `neutrals_in_radius` | `entity_list.neutrals_in_radius(center?: Entity\|Vector3, radius?: number) -> Entity[]` | safe | in_radius over designer names npc_neutral*. |
| `deployables_in_radius` | `entity_list.deployables_in_radius(center?: Entity\|Vector3, radius?: number) -> Entity[]` | safe | in_radius over designer names npc_bomber* / citadel_deploy*. |
| `find_by_name` | `entity_list.find_by_name(designer: string) -> Entity[]` | safe | Entities whose designer name (m_iszClassname, e.g. "npc_trooper") equals the string; at most 1024. Tick snapshot. |
| `get_class` | `entity_list.get_class(e: Entity) -> string` | safe | Designer name (m_iszClassname). Same function as Entity.GetClassName. |
| `get_entity_index` | `entity_list.get_entity_index(e: Entity) -> integer` | safe | Entry index; -1 for nil. Same function as Entity.GetEntityIndex. |
| `is_alive` | `entity_list.is_alive(e: Entity) -> boolean` | safe | Alive in the tick snapshot (a live read for an entity the frame does not hold yet). Same function as Entity.IsAlive. |
| `is_dormant` | `entity_list.is_dormant(e: Entity) -> boolean` | safe | Dormant in the tick snapshot (a live read for an entity the frame does not hold yet). |
| `distance_to` | `entity_list.distance_to(target: Entity\|Vector3) -> number` | safe | Units from the local camera to an entity's eye (the frame's measured distance, the engine's definition) or to a Vector3 or {x, y, z} point; 0 without a local pawn. |
| `distance_between` | `entity_list.distance_between(a: Entity\|Vector3, b: Entity\|Vector3) -> number` | safe | Units between two entity origins (from the tick snapshot) or Vector3 / {x, y, z} points; a missing argument is the local pawn's origin. |
| `dead_players` | `entity_list.dead_players() -> PlayerPawn[]` | safe | Player pawns dead in the tick snapshot (entity_list.players order). |
| `alive_players` | `entity_list.alive_players() -> PlayerPawn[]` | safe | Player pawns alive in the tick snapshot (entity_list.players order). |
| `abilities` | `entity_list.abilities() -> Ability[]` | safe | The local pawn's abilities, read live (the frame keeps no ability instances). |
| `modifiers` | `entity_list.modifiers() -> Modifier[]` | safe | The local pawn's modifiers, read live (the frame keeps no modifier instances). |

### db

`table` · tier `safe` — Persistent key/value store.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set` | `db.set(key: string, value: any)` | safe | Store a value (bool/number/string/table); nil deletes. |
| `get` | `db.get(key: string, default?: any) -> any` | safe | Read a value (returns default when absent). |
| `has` | `db.has(key: string) -> boolean` | safe | True if key is present. |
| `delete` | `db.delete(key: string)` | safe | Remove a key. |
| `keys` | `db.keys() -> string[]` | safe | List all string keys. |
| `clear` | `db.clear()` | safe | Remove every key in this script's namespace. |
| `save` | `db.save()` | safe | Force a flush to disk now (bypasses the ~1.5s throttle). |
| `__fieldstyle` | `.__fieldstyle: note` | safe | Field-style access is supported (umbrella_compat): db.foo reads through to db.get("foo") and db.foo = v writes through to db.set("foo", v). The explicit methods shadow same-named stored keys. |

### storage

`namespace` · tier `safe` — Typed key/value store, one namespace per script (keys are scoped to the calling script). A value keeps its type through save / load and to_json / from_json: an integer keeps all 64 bits and a number keeps full double precision.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set` | `storage.set(key: string, value: boolean\|integer\|number\|string\|nil) -> boolean` | safe | Store a value; nil deletes. false for any other type, a string over 256 KiB, or a script past its 4 MiB total. |
| `get` | `storage.get(key: string) -> boolean\|integer\|number\|string\|nil` | safe | The stored value, with the type it was stored with; nil when absent. |
| `save` | `storage.save() -> boolean` | safe | Write this script's keys to its storage file. |
| `load` | `storage.load() -> boolean` | safe | Read this script's keys back from its storage file. |
| `to_json` | `storage.to_json() -> string` | safe | This script's keys as one flat JSON object; integers are written exactly. |
| `from_json` | `storage.from_json(json: string) -> boolean` | safe | Merge a flat JSON object into this script's keys. A number without a '.' or an exponent is stored as a 64-bit integer. true when at least one key was applied. |

### convar

`table` · tier `safe` — Source2 ConVar table (convar.<name> -> lua_convar_t). nil for an unknown name, and for every name while the engine's ConVar access is unresolved (its patterns did not decode on this game build).

_No members._

### global_ctx

`table` · tier `safe` — Shared cross-script context table.

_No members._

### JSON

`table` · tier `safe` — JSON encode/decode helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `encode` | `JSON.encode(t: table, pretty?: boolean) -> string` | safe | Lua table -> JSON string (pretty default false). |
| `decode` | `JSON.decode(json: string) -> any` | safe | JSON string -> Lua value (nil on parse error). |
| `save` | `JSON.save(filename: string, t: table, pretty?: boolean) -> boolean` | privileged | Write table to ScriptData\<name>.json (pretty default TRUE). |
| `load` | `JSON.load(filename: string) -> any` | privileged | Read+parse ScriptData\<name>.json (nil on missing/parse error). |
| `exists` | `JSON.exists(filename: string) -> boolean` | privileged | ScriptData\<name>.json exists. |
| `delete` | `JSON.delete(filename: string) -> boolean` | privileged | Delete ScriptData\<name>.json. |
| `list` | `JSON.list() -> string[]` | privileged | Array of *.json filenames in ScriptData. |

### Math

`table` · tier `safe` — Extended math helpers (the globals Math and amath). Distances are in game units, except Distance / Distance2D and their _meters forms, which return meters (UNITS_TO_METERS).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `GetViewMatrix` | `Math.GetViewMatrix() -> table\|nil` | safe | Current 4x4 view-projection matrix (row-major table). |
| `GetViewport` | `Math.GetViewport() -> table\|nil` | safe | Current viewport { x, y, w, h }. |
| `WorldToScreenMatrix` | `Math.WorldToScreenMatrix(pos: Vector3) -> table\|nil` | safe | The same projection as Math.WorldToScreen (the engine's): { x, y, visible }, x = y = 0 when not visible; nil before the view matrix exists. |
| `UNITS_TO_METERS` | `.UNITS_TO_METERS: number` | safe | 0.0254: meters per game unit (the engine's constant). |
| `UNITS_PER_METER` | `.UNITS_PER_METER: number` | safe | Game units per meter (1 / 0.0254). |
| `UnitsToMeters` | `Math.UnitsToMeters(u: number) -> number` | safe |  |
| `MetersToUnits` | `Math.MetersToUnits(m: number) -> number` | safe |  |
| `Sign` | `Math.Sign(x: number) -> number` | safe | -1 / 0 / 1. |
| `Round` | `Math.Round(x: number) -> number` | safe | Round half away from zero. |
| `Approach` | `Math.Approach(current: number, target: number, step: number) -> number` | safe | Move current toward target by \|step\|, without overshooting. |
| `Remap` | `Math.Remap(x: number, in_min: number, in_max: number, out_min: number, out_max: number) -> number` | safe | Linear rescale between ranges (unbounded). |
| `RemapClamped` | `Math.RemapClamped(x: number, in_min: number, in_max: number, out_min: number, out_max: number) -> number` | safe | Linear rescale clamped to the output range. |
| `Map` | `Math.Map(x: number, in_min: number, in_max: number, out_min: number, out_max: number) -> number` | safe | Alias of Math.Remap. |
| `Snap` | `Math.Snap(x: number, step: number) -> number` | safe | Snap to the nearest multiple of step. |
| `SmoothStep` | `Math.SmoothStep(edge0: number, edge1: number, x: number) -> number` | safe | Hermite smoothstep (0..1). |
| `NormalizeYaw` | `Math.NormalizeYaw(angle: number) -> number` | safe | Wrap an angle/yaw to [-180, 180]. |
| `AngleDiff` | `Math.AngleDiff(a: number, b: number) -> number` | safe | Shortest signed angular difference a-b in [-180, 180]. |
| `Deg2Rad` | `Math.Deg2Rad(d: number) -> number` | safe |  |
| `Rad2Deg` | `Math.Rad2Deg(r: number) -> number` | safe |  |
| `InRange` | `Math.InRange(x: number, lo: number, hi: number) -> boolean` | safe |  |
| `AnglesToForward` | `Math.AnglesToForward(pitch: number, yaw: number) -> table` | safe | { x, y, z } unit forward vector for a pitch and yaw in degrees. |
| `Direction` | `Math.Direction(from: Vector3, to: Vector3) -> Vector3` | safe | Normalized direction from->to (zero if coincident). |
| `WorldToScreen` | `Math.WorldToScreen(worldPos: Vector3) -> table` | safe | Project a world point; returns { x, y, visible }. |
| `Distance` | `Math.Distance(pos1: Vector3, pos2: Vector3) -> number` | safe | 3D distance in METERS (units * UNITS_TO_METERS), despite the name; Distance_units returns units. |
| `Distance2D` | `Math.Distance2D(pos1: Vector3, pos2: Vector3) -> number` | safe | Horizontal (x, y) distance in METERS; ignores z. Distance2D_units returns units. |
| `Distance_meters` | `Math.Distance_meters(pos1: Vector3, pos2: Vector3) -> number` | safe | Same function as Math.Distance (meters). |
| `Distance_units` | `Math.Distance_units(pos1: Vector3, pos2: Vector3) -> number` | safe | 3D distance in game UNITS (same as Vector3:Distance). |
| `Distance2D_meters` | `Math.Distance2D_meters(pos1: Vector3, pos2: Vector3) -> number` | safe | Same function as Math.Distance2D (meters). |
| `Distance2D_units` | `Math.Distance2D_units(pos1: Vector3, pos2: Vector3) -> number` | safe | Horizontal (x, y) distance in game UNITS. |
| `dist2` | `Math.dist2(x1: number, y1: number, x2: number, y2: number) -> number` | safe | 2D distance in the inputs' units (game units for world x / y). |
| `dist3` | `Math.dist3(x1: number, y1: number, z1: number, x2: number, y2: number, z2: number) -> number` | safe | 3D distance in game UNITS. |
| `CalcAngle` | `Math.CalcAngle(from: Vector3, to: Vector3) -> Vector3` | safe | Euler angle from->to, packed as Vector3(pitch, yaw, roll) degrees. |
| `NormalizeAngle` | `Math.NormalizeAngle(angle: number) -> number` | safe | Wrap one angle to [-180,180]. |
| `Lerp` | `Math.Lerp(a: number, b: number, t: number) -> number` | safe | Scalar linear interpolation (t NOT clamped). |
| `Clamp` | `Math.Clamp(value: number, min: number, max: number) -> number` | safe | Clamp value to [min,max]. |
| `GetScreenCenter` | `Math.GetScreenCenter() -> table` | safe | Screen center { x, y } in pixels. |

### Game

`table` · tier `safe` — Game-state helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `GetLocalPlayer` | `Game.GetLocalPlayer() -> PlayerPawn\|nil` | safe | Local player pawn (nil if not up yet). |
| `GetAllPlayers` | `Game.GetAllPlayers() -> PlayerPawn[]` | safe | 1-indexed array of live CITADEL_PLAYER_PAWN entities. |
| `GetPlayerByIndex` | `Game.GetPlayerByIndex(index: integer) -> PlayerPawn\|nil` | safe | Same function as entity_list.by_index. |
| `IsInGame` | `Game.IsInGame() -> boolean` | safe | IVEngineToClient::IsInGame(). |

### Combat

`table` · tier `safe` — Combat helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `FindBestTarget` | `Combat.FindBestTarget(aim: AimConfig, eye: Vector3, angles: QAngle) -> PlayerPawn\|nil` | safe | Best ability-aim target. DORMANT: AimConfig cannot be constructed populated from Lua, so `aim` reads back as a default config — use GetBestScriptTarget. |
| `FindAllTargets` | `Combat.FindAllTargets(aim: AimConfig, eye: Vector3, angles: QAngle) -> PlayerPawn[]` | safe | All ability-aim targets. Same AimConfig dormancy caveat as FindBestTarget. |
| `GetBestScriptTarget` | `Combat.GetBestScriptTarget(eye: Vector3, angles: QAngle, max_range_m?: number, bone?: string, require_vis?: boolean) -> PlayerPawn\|nil` | safe | The usable script target picker. max_range_m is in METERS (default 50); bone default "spine_2"; require_vis default true. Tolerates nil/wrong-typed eye/angles (returns nil). |
| `IsTargetVisible` | `Combat.IsTargetVisible(eye_pos: Vector3, target_pos: Vector3, pawn: PlayerPawn) -> boolean` | safe | Line-of-sight from eye_pos to target_pos against `pawn`. |
| `ShouldIgnoreTarget` | `Combat.ShouldIgnoreTarget(pawn: PlayerPawn) -> boolean` | safe | True if the shared targeting policy says to skip this pawn. |
| `GetTargetHealth` | `Combat.GetTargetHealth(pawn: PlayerPawn) -> number` | safe | Current health. |
| `GetTargetMaxHealth` | `Combat.GetTargetMaxHealth(pawn: PlayerPawn) -> number` | safe | Max health. |
| `GetTargetHealthPercent` | `Combat.GetTargetHealthPercent(pawn: PlayerPawn) -> number` | safe | Health percent (0-100). |
| `GetTargetBaseHealth` | `Combat.GetTargetBaseHealth(pawn: PlayerPawn) -> number` | safe | Base (pre-barrier) current health. |
| `GetTargetBaseMaxHealth` | `Combat.GetTargetBaseMaxHealth(pawn: PlayerPawn) -> number` | safe | Base (pre-barrier) max health. |
| `GetBarrierHealth` | `Combat.GetBarrierHealth(pawn: PlayerPawn) -> number` | safe | Current barrier HP, from the pawn's modifier_barrier_tracker; 0 when it has none. Game-thread value, refreshed per tick. CHANGED: always returned 0 before. |
| `IsTargetBelowHealth` | `Combat.IsTargetBelowHealth(pawn: PlayerPawn, health_threshold: number) -> boolean` | safe | True if the pawn's health is below the threshold. |
| `RunMouseAimbot` | `Combat.RunMouseAimbot(target_pos: Vector3, speed?: number, deadzone?: number, max_per_frame?: number) -> boolean` | privileged | Drive the REAL hardware mouse toward target_pos. |
| `RunFastMouseAimbot` | `Combat.RunFastMouseAimbot(target_pos: Vector3) -> boolean` | privileged | Snap the REAL hardware mouse toward target_pos (fast path). |
| `GetAngleDiffToTarget` | `Combat.GetAngleDiffToTarget(eye_pos: Vector3, target_pos: Vector3, view_pitch: number, view_yaw: number) -> number` | safe | Angular error (degrees) between the view and the direction to target_pos. |
| `IsGameFocused` | `Combat.IsGameFocused() -> boolean` | safe | True when the game window has focus. |
| `ShouldRunFeatures` | `Combat.ShouldRunFeatures() -> boolean` | safe | True only when features may act: cheat menu CLOSED, game in play mode, window foregrounded, and the panic latch is clear. Stronger than IsGameFocused (which is just the window). Reactive features (auto-parry) should gate on this so they don't act while the menu/cursor is up. |

### player_stats

`table` · tier `safe` — Per-player bullet stats of the match from the game's damage messages.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `all` | `player_stats.all() -> table[]\|nil` | safe | One row per player on teams 2 / 3: { player_slot, team, hero_id, is_local, shots, hits, misses, headshots, damage_total, accuracy (%), headshot_percentage (% of hits) }. Shotgun pellets count as separate hits, so hits can pass shots (accuracy caps at 100). Counting starts on the first read and resets with the headshot tracker. nil before any count exists. Any thread. |

### AimConfig

`table` · tier `safe` — Aimbot configuration accessors.

_No members._

### Notification

`table` · tier `safe` — On-screen notification helpers.

_No members._

### Vertex

`table` · tier `safe` — Vertex constructor for polygon rendering.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `x` | `.x: number` | safe | Screen-space x (px). |
| `y` | `.y: number` | safe | Screen-space y (px). |
| `u` | `.u: number` | safe | Texture u (reserved for textured geometry). |
| `v` | `.v: number` | safe | Texture v (reserved). |
| `color` | `.color: Color` | safe | Per-vertex tint. |

### utils

`table` · tier `safe` — Misc script helpers: camera-aware eye/angles, distance, angle math, world->screen.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_camera_angles` | `utils.get_camera_angles() -> Angle` | safe | View angles captured this tick (the usercmd's pitch and yaw; roll 0). READ-ONLY. (0,0,0) before the first capture. |
| `set_camera_angles` | `utils.set_camera_angles(angles: Angle)` | safe | INTENTIONAL NO-OP: scripts must never write view/camera angles (aim spoofs camera POSITION only). Kept so callers don't nil-index. |
| `get_camera_pos` | `utils.get_camera_pos() -> Vector3` | safe | Camera position captured this tick: the usercmd camera position (camera-spoof aware) when set, else origin + view offset. (0,0,0) without a local pawn. |
| `calc_angle` | `utils.calc_angle(from: Vector3, to: Vector3) -> Angle` | safe | Euler angle pointing from `from` to `to`. |
| `distance` | `utils.distance(a: Vector3, b: Vector3) -> number` | safe | 3D distance in game UNITS. |
| `distance_2d` | `utils.distance_2d(a: Vector3, b: Vector3) -> number` | safe | 2D (XY) distance in game UNITS. |
| `get_game_time` | `utils.get_game_time() -> number` | safe | Current game time (m_flCurrentTime), seconds; 0 when unavailable. |
| `time_now` | `utils.time_now() -> number` | safe | Same function as get_game_time. |
| `world_to_screen` | `utils.world_to_screen(world_pos: Vector3) -> table` | safe | { x, y, visible } screen coords; visible = false when the point does not project (behind the camera). |
| `normalize_angle` | `utils.normalize_angle(angle: number) -> number` | safe | Wrap a degree angle into [-180, 180]. |
| `angle_diff` | `utils.angle_diff(a: number, b: number) -> number` | safe | Shortest signed difference a-b in degrees, wrapped to [-180, 180]. |
| `lerp` | `utils.lerp(a: number, b: number, t: number) -> number` | safe | Linear interpolation a + (b-a)*t (t not clamped). |
| `clamp` | `utils.clamp(value: number, min: number, max: number) -> number` | safe | Clamp value to [min, max]. |
| `execute_command` | `utils.execute_command(command: string) -> boolean` | safe | Run a client console command via IVEngineToClient::ExecuteClientCmd (e.g. "play <sound>"). COMMAND execution only, never a ConVar write. SEH-guarded; returns false (never throws) on an empty command, an unresolved engine interface, or a caught native fault. Your own panel: after "hud_free_cursor 1" and until "hud_free_cursor 0" (or your script unloads), clicks and wheel turns on the filled shapes your script draws (Render.FilledRect, FilledRectRounded, Gradient, FrostedFill, Image, draw.filled_rect; at least 8 px each way and not near-transparent) go to your script only, never the game. Mouse movement, keys and clicks anywhere else still reach the game, and nothing is taken while the game is in mouse look. |
| `get_fov` | `utils.get_fov(a: Angle, b: Angle) -> number` | safe | Degrees between the view directions of two angles (roll ignored): the FOV metric of HERO_LIB's get_fov_to_* and the script target picker. |
| `subclass_id` | `utils.subclass_id(name: string) -> integer` | safe | The engine string token of a vdata record or modifier name (C_BaseEntity::m_nSubclassID), unsigned: the id get_ability_by_id / has_item_by_id / has_modifier_by_id / Modifier:get_subclass_id use. |
| `get_vdata_by_subclass` | `utils.get_vdata_by_subclass(id: integer) -> table\|nil, string` | safe | A read-only schema view of the ability / item vdata record with that subclass id and its localization token ("#<record name>"); nil while no pawn carries the record. |
| `get_vdata_property` | `utils.get_vdata_property(id: integer, key: string) -> number\|nil` | safe | The base value (no upgrades) of an authored property of that record; nil without the record or the property. |

### draw

`namespace` · tier `safe` — Legacy 2D/3D draw helpers (render-stack; render-context only). color = a Color, or { r, g, b, a } by name or positional 1..4, each clamped to 0..255; a missing r, g or b is 0 and a missing a is 255 (the rule Render.* uses). No color draws white.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `text` | `draw.text(x: number, y: number, text: string, color?: Color\|table, font?: integer, align?: integer)` | safe | String via the render stack; align = Render.TEXT_ALIGN_* bits (default center). font is accepted and IGNORED: the default font always draws (Render.Text takes font handles). |
| `line` | `draw.line(x1: number, y1: number, x2: number, y2: number, color?: Color\|table, thickness?: number)` | safe | 2D line; thickness default 1. |
| `rect` | `draw.rect(x: number, y: number, w: number, h: number, color?: Color\|table, filled?: boolean, rounding?: number)` | safe | Rect at (x, y) size (w, h); rounding > 0 rounds the corners. |
| `circle` | `draw.circle(x: number, y: number, radius: number, color?: Color\|table, filled?: boolean)` | safe | 2D circle (radius in PIXELS). |
| `line_3d` | `draw.line_3d(x1: number, y1: number, z1: number, x2: number, y2: number, z2: number, color?: Color\|table, thickness?: number)` | safe | World-space line between two points (6 scalars). |
| `circle_3d` | `draw.circle_3d(x: number, y: number, z: number, radius: number, color?: Color\|table)` | safe | World-space circle at (x,y,z), radius in game UNITS. |
| `get_frame_time` | `draw.get_frame_time() -> number` | safe | Same value as Render.GetFrameTime. |
| `get_delta_time` | `draw.get_delta_time() -> number` | safe | Same value as Render.GetDeltaTime (the engine tick interval). |

### global_vars

`table` · tier `safe` — CGlobalVarsBase timing/frame accessors (raw clock). Each returns nil while the game's globals are not available.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `curtime` | `global_vars.curtime() -> number` | safe | m_flCurrentTimeRaw (RAW clock; 0.0 if globals null). |
| `latency_incoming` | `global_vars.latency_incoming() -> number` | safe | Round-trip latency of the connection in seconds, 0 when not connected. Deadlock measures one latency for both directions, so it equals latency_outgoing. |
| `latency_outgoing` | `global_vars.latency_outgoing() -> number` | safe | Round-trip latency of the connection in seconds, 0 when not connected (the same value as latency_incoming). |
| `tickcount` | `global_vars.tickcount() -> integer` | safe | m_nTickCount (0 if null). |
| `framecount` | `global_vars.framecount() -> integer` | safe | m_nFrameCount (0 if null). |
| `interval_per_tick` | `global_vars.interval_per_tick() -> number` | safe | m_flIntervalPerTick (0.015 fallback if null). |
| `realtime` | `global_vars.realtime() -> number` | safe | m_flRealTime (0.0 if null). |
| `frametime` | `global_vars.frametime() -> number` | safe | m_flAbsoluteFrameTime (0.0 if null). |
| `max_clients` | `global_vars.max_clients() -> integer` | safe | m_nMaxClients (32 fallback if null). |
| `tick_interval` | `global_vars.tick_interval() -> number` | safe | SAME field as interval_per_tick. |
| `server_time` | `global_vars.server_time() -> number` | safe | SAME field as curtime (m_flCurrentTimeRaw). |
| `map_name` | `global_vars.map_name() -> string` | safe | GetMapName() ("unknown" if null). |

### game_rules

`table` · tier `safe` — Game-rules clock (PAUSE-ADJUSTED time; differs from global_vars raw clock).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `game_time` | `game_rules.game_time() -> number` | safe | m_flCurrentTime (PAUSE-ADJUSTED clock; differs from global_vars.curtime). |
| `tick_interval` | `game_rules.tick_interval() -> number` | safe | m_flIntervalPerTick (1/64 fallback). |

### io

`namespace` · tier `privileged` — Sandboxed file I/O (rooted at %APPDATA%\Avalanche\ScriptFiles). TRUSTED/local.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `open` | `io.open(filename: string, mode?: string) -> File?` | privileged | Open a file (mode default "r"); File handle \| nil. RELATIVE paths are sandboxed under %APPDATA%\Avalanche\ScriptFiles; ABSOLUTE paths are honored as-is (io is trusted-only, so this is the authorized absolute-path access for trusted/local scripts — Steam vdf/avatarcache reads, assets next to the script, config import/export). |
| `exists` | `io.exists(filename: string) -> boolean` | privileged | Sandboxed path exists. |
| `remove` | `io.remove(filename: string) -> boolean` | privileged | Delete a sandboxed file. |
| `rename` | `io.rename(oldname: string, newname: string) -> boolean` | privileged | Rename within the sandbox (false on failure). |
| `lines` | `io.lines(filename: string) -> string[]` | privileged | 1-indexed array of the file's lines (empty if unopenable). |

### QAngle

`usertype` · tier `safe` — Euler angle value type (pitch, yaw, roll degrees) passed by value into the Combat targeting helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `pitch` | `.pitch: number` | safe | Pitch (m_x), degrees. |
| `yaw` | `.yaw: number` | safe | Yaw (m_y), degrees. |
| `roll` | `.roll: number` | safe | Roll (m_z), degrees. |

### InputBitMask_t

`table` · tier `safe` — CUserCmd button bit constants (uint64 flags ORed into cmd:add_buttonstate*).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `IN_ATTACK` | `.IN_ATTACK: integer` | safe | 0x1 |
| `IN_JUMP` | `.IN_JUMP: integer` | safe | 0x2 |
| `IN_DUCK` | `.IN_DUCK: integer` | safe | 0x4 |
| `IN_FORWARD` | `.IN_FORWARD: integer` | safe | 0x8 |
| `IN_BACK` | `.IN_BACK: integer` | safe | 0x10 |
| `IN_USE` | `.IN_USE: integer` | safe | 0x20 |
| `IN_TURNLEFT` | `.IN_TURNLEFT: integer` | safe | 0x80 |
| `IN_TURNRIGHT` | `.IN_TURNRIGHT: integer` | safe | 0x100 |
| `IN_MOVELEFT` | `.IN_MOVELEFT: integer` | safe | 0x200 |
| `IN_MOVERIGHT` | `.IN_MOVERIGHT: integer` | safe | 0x400 |
| `IN_ATTACK2` | `.IN_ATTACK2: integer` | safe | 0x800 |
| `IN_RELOAD` | `.IN_RELOAD: integer` | safe | 0x2000 |
| `IN_SPEED` | `.IN_SPEED: integer` | safe | 0x10000 |
| `IN_JOYAUTOSPRINT` | `.IN_JOYAUTOSPRINT: integer` | safe | 0x20000 |
| `IN_WEAPON1` | `.IN_WEAPON1: integer` | safe | 0x100000000 |
| `IN_ABILITY1` | `.IN_ABILITY1: integer` | safe | 0x200000000 |
| `IN_ABILITY2` | `.IN_ABILITY2: integer` | safe | 0x400000000 |
| `IN_ABILITY3` | `.IN_ABILITY3: integer` | safe | 0x800000000 |
| `IN_ABILITY4` | `.IN_ABILITY4: integer` | safe | 0x1000000000 |
| `IN_ITEM1` | `.IN_ITEM1: integer` | safe | 0x2000000000 |
| `IN_ITEM2` | `.IN_ITEM2: integer` | safe | 0x4000000000 |
| `IN_ITEM3` | `.IN_ITEM3: integer` | safe | 0x8000000000 |
| `IN_ITEM4` | `.IN_ITEM4: integer` | safe | 0x10000000000 |
| `IN_ITEM5` | `.IN_ITEM5: integer` | safe | 0x20000000000 |
| `IN_ABILITY_HELD` | `.IN_ABILITY_HELD: integer` | safe | 0x40000000000 |
| `IN_INNATE_1` | `.IN_INNATE_1: integer` | safe | 0x100000000000 |
| `IN_INNATE_2` | `.IN_INNATE_2: integer` | safe | 0x200000000000 |
| `IN_INNATE_3` | `.IN_INNATE_3: integer` | safe | 0x400000000000 |
| `IN_MANTLE` | `.IN_MANTLE: integer` | safe | 0x1000000000000 |
| `IN_SPEC_NEXT` | `.IN_SPEC_NEXT: integer` | safe | 0x2000000000000 |
| `IN_SPEC_PREV` | `.IN_SPEC_PREV: integer` | safe | 0x4000000000000 |
| `IN_SPEC_MODE` | `.IN_SPEC_MODE: integer` | safe | 0x8000000000000 |
| `IN_SPEC_TOGGLE_TEAM` | `.IN_SPEC_TOGGLE_TEAM: integer` | safe | 0x10000000000000 |
| `IN_ALT_CAST` | `.IN_ALT_CAST: integer` | safe | 0x20000000000000 |
| `IN_REPLAY_DEATH` | `.IN_REPLAY_DEATH: integer` | safe | 0x40000000000000 |
| `IN_TELEPORT` | `.IN_TELEPORT: integer` | safe | 0x80000000000000 |
| `IN_ZIPLINE` | `.IN_ZIPLINE: integer` | safe | 0x100000000000000 |
| `IN_MOVE_UP` | `.IN_MOVE_UP: integer` | safe | 0x200000000000000 |
| `IN_MOVE_DOWN` | `.IN_MOVE_DOWN: integer` | safe | 0x400000000000000 |
| `IN_DUCK_TOGGLE` | `.IN_DUCK_TOGGLE: integer` | safe | 0x800000000000000 |
| `IN_CANCEL_ABILITY` | `.IN_CANCEL_ABILITY: integer` | safe | 0x1000000000000000 |
| `IN_COSMETIC_1` | `.IN_COSMETIC_1: integer` | safe | 0x2000000000000000 |
| `IN_DOWN_DASH` | `.IN_DOWN_DASH: integer` | safe | 0x4000000000000000 |

### Enum.ButtonCode

`table` · tier `safe` — Source 2 ButtonCode_t key ordinals in the engine's order (KEY_NONE = 0, KEY_0 = 1, ...; MenuNode:Bind default-key seeds).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `KEY_NONE` | `.KEY_NONE: integer` | safe | 0 |
| `KEY_0` | `.KEY_0: integer` | safe | 1 |
| `KEY_1` | `.KEY_1: integer` | safe | 2 |
| `KEY_2` | `.KEY_2: integer` | safe | 3 |
| `KEY_3` | `.KEY_3: integer` | safe | 4 |
| `KEY_4` | `.KEY_4: integer` | safe | 5 |
| `KEY_5` | `.KEY_5: integer` | safe | 6 |
| `KEY_6` | `.KEY_6: integer` | safe | 7 |
| `KEY_7` | `.KEY_7: integer` | safe | 8 |
| `KEY_8` | `.KEY_8: integer` | safe | 9 |
| `KEY_9` | `.KEY_9: integer` | safe | 10 |
| `KEY_A` | `.KEY_A: integer` | safe | 11 |
| `KEY_B` | `.KEY_B: integer` | safe | 12 |
| `KEY_C` | `.KEY_C: integer` | safe | 13 |
| `KEY_D` | `.KEY_D: integer` | safe | 14 |
| `KEY_E` | `.KEY_E: integer` | safe | 15 |
| `KEY_F` | `.KEY_F: integer` | safe | 16 |
| `KEY_G` | `.KEY_G: integer` | safe | 17 |
| `KEY_H` | `.KEY_H: integer` | safe | 18 |
| `KEY_I` | `.KEY_I: integer` | safe | 19 |
| `KEY_J` | `.KEY_J: integer` | safe | 20 |
| `KEY_K` | `.KEY_K: integer` | safe | 21 |
| `KEY_L` | `.KEY_L: integer` | safe | 22 |
| `KEY_M` | `.KEY_M: integer` | safe | 23 |
| `KEY_N` | `.KEY_N: integer` | safe | 24 |
| `KEY_O` | `.KEY_O: integer` | safe | 25 |
| `KEY_P` | `.KEY_P: integer` | safe | 26 |
| `KEY_Q` | `.KEY_Q: integer` | safe | 27 |
| `KEY_R` | `.KEY_R: integer` | safe | 28 |
| `KEY_S` | `.KEY_S: integer` | safe | 29 |
| `KEY_T` | `.KEY_T: integer` | safe | 30 |
| `KEY_U` | `.KEY_U: integer` | safe | 31 |
| `KEY_V` | `.KEY_V: integer` | safe | 32 |
| `KEY_W` | `.KEY_W: integer` | safe | 33 |
| `KEY_X` | `.KEY_X: integer` | safe | 34 |
| `KEY_Y` | `.KEY_Y: integer` | safe | 35 |
| `KEY_Z` | `.KEY_Z: integer` | safe | 36 |
| `KEY_PAD_0` | `.KEY_PAD_0: integer` | safe | 37 |
| `KEY_PAD_1` | `.KEY_PAD_1: integer` | safe | 38 |
| `KEY_PAD_2` | `.KEY_PAD_2: integer` | safe | 39 |
| `KEY_PAD_3` | `.KEY_PAD_3: integer` | safe | 40 |
| `KEY_PAD_4` | `.KEY_PAD_4: integer` | safe | 41 |
| `KEY_PAD_5` | `.KEY_PAD_5: integer` | safe | 42 |
| `KEY_PAD_6` | `.KEY_PAD_6: integer` | safe | 43 |
| `KEY_PAD_7` | `.KEY_PAD_7: integer` | safe | 44 |
| `KEY_PAD_8` | `.KEY_PAD_8: integer` | safe | 45 |
| `KEY_PAD_9` | `.KEY_PAD_9: integer` | safe | 46 |
| `KEY_PAD_DIVIDE` | `.KEY_PAD_DIVIDE: integer` | safe | 47 |
| `KEY_PAD_MULTIPLY` | `.KEY_PAD_MULTIPLY: integer` | safe | 48 |
| `KEY_PAD_MINUS` | `.KEY_PAD_MINUS: integer` | safe | 49 |
| `KEY_PAD_PLUS` | `.KEY_PAD_PLUS: integer` | safe | 50 |
| `KEY_PAD_ENTER` | `.KEY_PAD_ENTER: integer` | safe | 51 |
| `KEY_PAD_DECIMAL` | `.KEY_PAD_DECIMAL: integer` | safe | 52 |
| `KEY_LBRACKET` | `.KEY_LBRACKET: integer` | safe | 53 |
| `KEY_RBRACKET` | `.KEY_RBRACKET: integer` | safe | 54 |
| `KEY_SEMICOLON` | `.KEY_SEMICOLON: integer` | safe | 55 |
| `KEY_APOSTROPHE` | `.KEY_APOSTROPHE: integer` | safe | 56 |
| `KEY_BACKQUOTE` | `.KEY_BACKQUOTE: integer` | safe | 57 |
| `KEY_COMMA` | `.KEY_COMMA: integer` | safe | 58 |
| `KEY_PERIOD` | `.KEY_PERIOD: integer` | safe | 59 |
| `KEY_SLASH` | `.KEY_SLASH: integer` | safe | 60 |
| `KEY_BACKSLASH` | `.KEY_BACKSLASH: integer` | safe | 61 |
| `KEY_MINUS` | `.KEY_MINUS: integer` | safe | 62 |
| `KEY_EQUAL` | `.KEY_EQUAL: integer` | safe | 63 |
| `KEY_ENTER` | `.KEY_ENTER: integer` | safe | 64 |
| `KEY_SPACE` | `.KEY_SPACE: integer` | safe | 65 |
| `KEY_BACKSPACE` | `.KEY_BACKSPACE: integer` | safe | 66 |
| `KEY_TAB` | `.KEY_TAB: integer` | safe | 67 |
| `KEY_CAPSLOCK` | `.KEY_CAPSLOCK: integer` | safe | 68 |
| `KEY_NUMLOCK` | `.KEY_NUMLOCK: integer` | safe | 69 |
| `KEY_ESCAPE` | `.KEY_ESCAPE: integer` | safe | 70 |
| `KEY_SCROLLLOCK` | `.KEY_SCROLLLOCK: integer` | safe | 71 |
| `KEY_INSERT` | `.KEY_INSERT: integer` | safe | 72 |
| `KEY_DELETE` | `.KEY_DELETE: integer` | safe | 73 |
| `KEY_HOME` | `.KEY_HOME: integer` | safe | 74 |
| `KEY_END` | `.KEY_END: integer` | safe | 75 |
| `KEY_PAGEUP` | `.KEY_PAGEUP: integer` | safe | 76 |
| `KEY_PAGEDOWN` | `.KEY_PAGEDOWN: integer` | safe | 77 |
| `KEY_BREAK` | `.KEY_BREAK: integer` | safe | 78 |
| `KEY_LSHIFT` | `.KEY_LSHIFT: integer` | safe | 79 |
| `KEY_RSHIFT` | `.KEY_RSHIFT: integer` | safe | 80 |
| `KEY_LALT` | `.KEY_LALT: integer` | safe | 81 |
| `KEY_RALT` | `.KEY_RALT: integer` | safe | 82 |
| `KEY_LCONTROL` | `.KEY_LCONTROL: integer` | safe | 83 |
| `KEY_RCONTROL` | `.KEY_RCONTROL: integer` | safe | 84 |
| `KEY_LWIN` | `.KEY_LWIN: integer` | safe | 85 |
| `KEY_RWIN` | `.KEY_RWIN: integer` | safe | 86 |
| `KEY_APP` | `.KEY_APP: integer` | safe | 87 |
| `KEY_UP` | `.KEY_UP: integer` | safe | 88 |
| `KEY_LEFT` | `.KEY_LEFT: integer` | safe | 89 |
| `KEY_DOWN` | `.KEY_DOWN: integer` | safe | 90 |
| `KEY_RIGHT` | `.KEY_RIGHT: integer` | safe | 91 |
| `KEY_F1` | `.KEY_F1: integer` | safe | 92 |
| `KEY_F2` | `.KEY_F2: integer` | safe | 93 |
| `KEY_F3` | `.KEY_F3: integer` | safe | 94 |
| `KEY_F4` | `.KEY_F4: integer` | safe | 95 |
| `KEY_F5` | `.KEY_F5: integer` | safe | 96 |
| `KEY_F6` | `.KEY_F6: integer` | safe | 97 |
| `KEY_F7` | `.KEY_F7: integer` | safe | 98 |
| `KEY_F8` | `.KEY_F8: integer` | safe | 99 |
| `KEY_F9` | `.KEY_F9: integer` | safe | 100 |
| `KEY_F10` | `.KEY_F10: integer` | safe | 101 |
| `KEY_F11` | `.KEY_F11: integer` | safe | 102 |
| `KEY_F12` | `.KEY_F12: integer` | safe | 103 |
| `to_vk` | `Enum.ButtonCode.to_vk(code: integer) -> integer` | safe | The Windows VK of a ButtonCode, 0 when it has none. |
| `from_vk` | `Enum.ButtonCode.from_vk(vk: integer) -> integer` | safe | The ButtonCode of a Windows VK, KEY_NONE (0) when it has none. |

### Enum.GroupSide

`table` · tier `safe` — Heroes-page column side hint (Left/Right/Both).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Left` | `.Left: integer` | safe | 0 |
| `Right` | `.Right: integer` | safe | 1 |
| `Both` | `.Both: integer` | safe | 2 |

### Enum.ImageFilter

`table` · tier `safe` — Image filter hint (None/White).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `None` | `.None: integer` | safe | 0 |
| `White` | `.White: integer` | safe | 1 |

### EAbilitySlots_t

`table` · tier `safe` — Semantic ability/item slot ordinals (m_eAbilitySlot).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ESlot_Signature_1` | `.ESlot_Signature_1: integer` | safe | 0 |
| `ESlot_Signature_2` | `.ESlot_Signature_2: integer` | safe | 1 |
| `ESlot_Signature_3` | `.ESlot_Signature_3: integer` | safe | 2 |
| `ESlot_Signature_4` | `.ESlot_Signature_4: integer` | safe | 3 |
| `ESlot_Ability_0` | `.ESlot_Ability_0: integer` | safe | 0 (alias of Signature_1) |
| `ESlot_Ability_1` | `.ESlot_Ability_1: integer` | safe | 1 (alias of Signature_2) |
| `ESlot_Ability_2` | `.ESlot_Ability_2: integer` | safe | 2 (alias of Signature_3) |
| `ESlot_Ability_3` | `.ESlot_Ability_3: integer` | safe | 3 (alias of Signature_4) |
| `ESlot_ActiveItem_1` | `.ESlot_ActiveItem_1: integer` | safe | 4 |
| `ESlot_ActiveItem_2` | `.ESlot_ActiveItem_2: integer` | safe | 5 |
| `ESlot_ActiveItem_3` | `.ESlot_ActiveItem_3: integer` | safe | 6 |
| `ESlot_ActiveItem_4` | `.ESlot_ActiveItem_4: integer` | safe | 7 |
| `ESlot_Ability_Mantle` | `.ESlot_Ability_Mantle: integer` | safe | 10 |
| `ESlot_Ability_Jump` | `.ESlot_Ability_Jump: integer` | safe | 12 |
| `ESlot_Ability_Slide` | `.ESlot_Ability_Slide: integer` | safe | 13 |
| `ESlot_Ability_Innate_1` | `.ESlot_Ability_Innate_1: integer` | safe | 17 |

### ModifierValue

`table` · tier `safe` — Friendly names for common EModifierValue numbers (TechPower, WeaponPower, BulletDamage, AbilityCooldownReduction, BulletLifestealPercent, AbilityLifestealPercent, MaxHealth, HealthRegen, BulletResist, TechResist). CHANGED: each name now carries the live schema number of its EModifierValue enumerator (-1 when the build lacks it). The old 0..9 numbers were made up, so a script that passes a raw 0..9 literal to get_modifier_value now asks for a different value; scripts that use the names are unaffected.

_No members._

### EModifierValue

`table` · tier `safe` — The game's EModifierValue from the live schema, both ways: EModifierValue.MODIFIER_VALUE_TECH_POWER -> number and number -> name. The numbers shift between game builds, so always pass a name's value to get_modifier_value. Empty when the schema lacks the enum.

_No members._

### WeaponBulletData

`usertype` · tier `safe` — Local weapon bullet physics returned by Aim.GetBulletPhysics.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Speed` | `.Speed: number` | safe | Bullet speed (game units/sec). |
| `Gravity` | `.Gravity: number` | safe | Bullet drop in units/s^2 (m_flBulletGravityScale x sv_gravity, 800 on standard servers; 0 = no drop). The BASE scale: a weapon with a gravity-by-distance curve (Rat King) drops differently with range; prediction.gravity(nil, distance) gives that. |
| `Radius` | `.Radius: number` | safe | Bullet hull radius (game units). |
| `WorldRadius` | `.WorldRadius: number` | safe | World-collision radius (game units). |
| `InheritVelScale` | `.InheritVelScale: number` | safe | Fraction of shooter velocity inherited by the projectile. |
| `Valid` | `.Valid: boolean` | safe | True when the physics were resolved for the local weapon. |

### AimResult

`usertype` · tier `safe` — Projectile aim solution returned by Aim.AimAt*/Solve.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `FakePos` | `.FakePos: Vector3` | safe | Camera/aim position to publish (position-only PSilent point). |
| `PredictedImpact` | `.PredictedImpact: Vector3` | safe | Predicted bullet impact point. |
| `FlightTime` | `.FlightTime: number` | safe | Projectile flight time (seconds). |
| `ArchHeight` | `.ArchHeight: number` | safe | Arc apex height (game units). |
| `CamOffset` | `.CamOffset: number` | safe | Scalar camera offset applied. |
| `AimpointShift` | `.AimpointShift: number` | safe | Scalar aim-point shift applied. |
| `Valid` | `.Valid: boolean` | safe | True if a firing solution was found. |
| `Reason` | `.Reason: integer` | safe | AimFailReason enum value (0 = OK). |

### PlayerTarget

`usertype` · tier `safe` — Script-built player-bone aim target; construct via PlayerTarget().

| Member | Signature | Tier | Description |
|---|---|---|---|
| `BonePos` | `.BonePos: Vector3` | safe | Target bone/world position (game units). |
| `BoneVel` | `.BoneVel: Vector3` | safe | Target velocity (units/sec) for lead prediction. |
| `BodyRadius` | `.BodyRadius: number` | safe | Effective body radius (game units, default 20). |
| `EntityIdx` | `.EntityIdx: integer` | safe | Entity index of the target. |
| `SmoothingAlpha` | `.SmoothingAlpha: number` | safe | Aim smoothing factor 0..1 (default 0.6). |

### SoulTarget

`usertype` · tier `safe` — Script-built soul-orb aim target; construct via SoulTarget().

| Member | Signature | Tier | Description |
|---|---|---|---|
| `CurrentPos` | `.CurrentPos: Vector3` | safe | Soul orb current position (game units). |
| `CurrentVel` | `.CurrentVel: Vector3` | safe | Soul orb current velocity (units/sec). |

### DeployableTarget

`usertype` · tier `safe` — Script-built deployable/area aim target; construct via DeployableTarget().

| Member | Signature | Tier | Description |
|---|---|---|---|
| `CenterPos` | `.CenterPos: Vector3` | safe | Deployable center (game units). |
| `Radius` | `.Radius: number` | safe | Deployable radius (game units, default 30). |

### AimInput

`usertype` · tier `safe` — Fully-specified projectile solve input; construct via AimInput().

| Member | Signature | Tier | Description |
|---|---|---|---|
| `EyePos` | `.EyePos: Vector3` | safe | Shooter eye position (game units). |
| `ViewDir` | `.ViewDir: Vector3` | safe | Shooter view direction (unit vector). |
| `TargetPos` | `.TargetPos: Vector3` | safe | Target position (game units). |
| `TargetRadius` | `.TargetRadius: number` | safe | Target radius (game units, default 20). |
| `HitTolerance` | `.HitTolerance: number` | safe | Hit tolerance slack (game units, default 18). |
| `BulletSpeed` | `.BulletSpeed: number` | safe | Projectile speed (units/sec; 0 = hitscan). |
| `BulletGravity` | `.BulletGravity: number` | safe | Projectile gravity scalar (0 = none). |
| `MinForwardDist` | `.MinForwardDist: number` | safe | Minimum forward distance before a solution is valid (units, default 50). |

### AimFailReason

`table` · tier `safe` — AimResult.Reason enum constants.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `OK` | `.OK: integer` | safe | 0 — solution found. |
| `TargetTooClose` | `.TargetTooClose: integer` | safe | 1 — target inside MinForwardDist. |
| `TargetBehindView` | `.TargetBehindView: integer` | safe | 2 — target behind the view plane. |
| `InvalidBulletPhysics` | `.InvalidBulletPhysics: integer` | safe | 3 — bullet physics unresolved. |
| `ZeroViewDir` | `.ZeroViewDir: integer` | safe | 4 — degenerate (zero-length) view direction. |
| `OutOfPSilentReach` | `.OutOfPSilentReach: integer` | safe | DEPRECATED: fixed -1 sentinel; reach is a magnitude clamp, never a fail reason. |

### lua_raw_ptr_t

`usertype` · tier `safe` — INERT raw-pointer handle — Avalanche exposes no script-side RPM/WPM; surfaced so a binding does not nil-crash.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `read` | `:read() -> nil` | safe | INERT: always nil. Avalanche exposes NO script-side RPM; surfaced only so a binding does not nil-crash. |
| `write` | `:write(a: any, b: any) -> nil` | safe | INERT no-op. No script-side WPM in Avalanche. |

## Global functions

Callable from any script without a scope prefix.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set_timeout` | `set_timeout(fn: fun(), seconds: number) -> integer` | safe | Arm a one-shot timer; returns id (0 on invalid). |
| `set_interval` | `set_interval(fn: fun(), seconds: number) -> integer` | safe | Arm a repeating timer; returns id (0 on invalid). |
| `clear_timeout` | `clear_timeout(id: integer) -> boolean` | safe | Cancel a timer by id. |
| `clear_interval` | `clear_interval(id: integer) -> boolean` | safe | Cancel an interval by id (same impl as clear_timeout). |
| `has_capability` | `has_capability(name: string) -> boolean` | safe | INFORMATIONAL self-check: is a capability (mem/hooks/native/ffi/native_call/mem.write/http/schema.raw_read/panorama) granted to the calling script? Unknown names return false. Overwriting this in your env changes nothing the host does. |
| `set_thread_safe_reads` | `set_thread_safe_reads(enabled: boolean)` | safe | Per-script opt-out of snapshot-routed entity reads. Default true (SAFE): render-thread entity scalar reads come from an immutable per-tick snapshot. false => LIVE reads on the render thread too (author owns the thread-affinity risk). |
| `execute_after` | `execute_after(delay: number, fn: function) -> integer\|nil` | safe | Deferred game-thread call (alias of common.execute_after). |
| `raw_struct` | `raw_struct(address: integer, class?: string) -> raw_struct` | privileged | Construct a typed view over a native struct pointer (optional schema class name for by-name field access). |
| `QAngle` | `QAngle(pitch?: number, yaw?: number, roll?: number) -> QAngle` | safe | Construct a QAngle; fewer than 3 args -> zero angle. |
| `Angle` | `Angle(pitch?: number, yaw?: number, roll?: number) -> Angle` | safe | Construct an Angle; fewer than 3 args -> zero angle (supports + - * and tostring). |
| `PlayerTarget` | `PlayerTarget() -> PlayerTarget` | safe | Construct an empty player aim target. |
| `SoulTarget` | `SoulTarget() -> SoulTarget` | safe | Construct an empty soul aim target. |
| `DeployableTarget` | `DeployableTarget() -> DeployableTarget` | safe | Construct an empty deployable aim target. |
| `AimInput` | `AimInput() -> AimInput` | safe | Construct an empty projectile solve input. |
| `Vertex` | `Vertex(x?: number, y?: number, u?: number, v?: number, color?: Color) -> Vertex` | safe | Construct a polygon vertex; Vertex() / (x,y) / (x,y,u,v) / (x,y,u,v,color). |
| `__avalanche_dbglog` | `__avalanche_dbglog(msg: any) -> nil` | safe | Release-active diagnostic print (-> DEV_LOG / OutputDebugString). The only visible print bridge in Release. |

## Callbacks

Register a handler and the engine calls it on the matching event.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_createmove` | `on_createmove(cmd: UserCmd)` | safe |  |
| `on_pre_frame` | `on_pre_frame()` | safe |  |
| `on_frame` | `on_frame()` | safe |  |
| `on_post_frame` | `on_post_frame()` | safe |  |
| `on_pre_framestage` | `on_pre_framestage(stage: integer)` | safe |  |
| `on_post_framestage` | `on_post_framestage(stage: integer)` | safe |  |
| `on_map_load_start` | `on_map_load_start()` | safe | Map load begins (before pawn spawn). |
| `on_map_load_full` | `on_map_load_full()` | safe | Local pawn spawned into a live match. |
| `on_game_start` | `on_game_start()` | safe | The match went live (game state -> GameInProgress, 7). CHANGED: used to fire at WaitForMapToLoad. |
| `on_game_end` | `on_game_end(winner_team: integer)` | safe | The match ended (game state -> PostGame, 8); the winning team is passed. CHANGED: used to fire at PreGameWait. |
| `on_round_start` | `on_round_start()` | safe | The game rules' round start time changed. |
| `on_round_end` | `on_round_end(winner_team: integer)` | safe | Fires with on_game_end when a round was live. |
| `on_render` | `on_render()` | safe |  |
| `on_entity_created` | `on_entity_created(entity: Entity, idx: integer)` | safe |  |
| `on_entity_deleted` | `on_entity_deleted(entity: Entity\|nil, idx: integer)` | safe |  |
| `on_modifier_added` | `on_modifier_added(mod: lightuserdata, holder_handle: lightuserdata, modifier: Modifier\|nil, target: PlayerPawn\|Entity\|nil, caster: PlayerPawn\|Entity\|nil)` | safe | Game thread. A modifier (buff/debuff) was added to an entity. Handlers get (mod, holder_handle, modifier, target, caster): mod is the modifier and holder_handle the holder's entity handle, both light userdata (as before); modifier is the Modifier usertype; target is the entity holding it and caster the modifier's caster (PlayerPawn for a hero pawn, else Entity; nil when gone). The last three are nil off the game thread. CHANGED: the last three arguments are new; earlier docs called the first two (Modifier, PlayerPawn), which they never were. Alias of on_add_modifier. |
| `on_modifier_removed` | `on_modifier_removed(mod: lightuserdata, holder_handle: lightuserdata, modifier_name: string\|nil, target: PlayerPawn\|Entity\|nil, caster: PlayerPawn\|Entity\|nil)` | safe | Game thread. Fires just BEFORE the engine frees a modifier: read it now, do NOT retain the pointer. Handlers get (mod, holder_handle, modifier_name, target, caster): mod and holder_handle are light userdata as before; modifier_name is the modifier's name (the modifier is freed right after the event); target / caster as on_add_modifier. CHANGED: the last three arguments are new. Alias of on_remove_modifier. |
| `on_fire_bullets` | `on_fire_bullets(ctx: any)` | safe | Game thread. Defined by a script: called with an opaque bullet context. Called as on_fire_bullets(fn): registers fn on bullet_create, exactly like on_bullet_create. |
| `on_take_damage` | `on_take_damage(ev: any, name: string)` | safe |  |
| `on_particle_create` | `on_particle_create(ctx: any)` | safe |  |
| `on_game_event` | `on_game_event(ev: GameEvent, name: string)` | safe |  |
| `on_user_message` | `on_user_message(id: integer, bytes: string) -> boolean` | safe |  |
| `on_net_message` | `on_net_message(id: integer, bytes: string) -> boolean` | safe |  |
| `on_draw` | `on_draw()` | safe | Primary render callback — fires every frame on the RENDER thread. Do 2D/3D drawing (Render / ImGui / Aim world-to-screen) here, not game-thread entity reads. |
| `on_pre_createmove` | `on_pre_createmove(cmd: UserCmd)` | safe | Game thread. Runs just BEFORE on_createmove on the same per-tick UserCmd — for logic that must precede the main movement/aim handler. |
| `on_add_modifier` | `on_add_modifier(mod: lightuserdata, holder_handle: lightuserdata, modifier: Modifier\|nil, target: PlayerPawn\|Entity\|nil, caster: PlayerPawn\|Entity\|nil)` | safe | Game thread. A modifier (buff/debuff) was added to an entity. Handlers get (mod, holder_handle, modifier, target, caster): mod is the modifier and holder_handle the holder's entity handle, both light userdata (as before); modifier is the Modifier usertype; target is the entity holding it and caster the modifier's caster (PlayerPawn for a hero pawn, else Entity; nil when gone). The last three are nil off the game thread. CHANGED: the last three arguments are new; earlier docs called the first two (Modifier, PlayerPawn), which they never were. Alias of on_modifier_added (same handler slot). |
| `on_remove_modifier` | `on_remove_modifier(mod: lightuserdata, holder_handle: lightuserdata, modifier_name: string\|nil, target: PlayerPawn\|Entity\|nil, caster: PlayerPawn\|Entity\|nil)` | safe | Game thread. Fires just BEFORE the engine frees a modifier: read it now, do NOT retain the pointer. Handlers get (mod, holder_handle, modifier_name, target, caster): mod and holder_handle are light userdata as before; modifier_name is the modifier's name (the modifier is freed right after the event); target / caster as on_add_modifier. CHANGED: the last three arguments are new. Alias of on_modifier_removed (same handler slot). |
| `on_bullet_create` | `on_bullet_create(data: table)` | safe | Game thread. A bullet/hitscan was fired. data = { origin, start_pos, direction, angles, max_range, shooter:PlayerPawn, weapon_name, ... }. Alias of on_fire_bullets (same handler slot). |
| `on_particle_update` | `on_particle_update(data: table)` | safe | Game thread. A tracked particle effect updated. data = { path:string, index:integer, position:Vector3 }. |
| `on_particle_destroy` | `on_particle_destroy(data: table)` | safe | Game thread. A tracked particle effect was destroyed. data = { path:string, index:integer } (no position). |
| `on_key_event` | `on_key_event(key: integer, down: boolean) -> boolean` | safe | WndProc thread. key = virtual key code, down = pressed(true)/released(false). RETURN-GATED: return a truthy value to SWALLOW the key (block it from the game). |
| `on_key` | `on_key(key: integer, down: boolean) -> boolean` | safe | Alias of on_key_event (same handler slot). WndProc thread. Return truthy to swallow the key. |
| `on_entity_create` | `on_entity_create(entity: Entity, idx: integer)` | safe | Game thread. An entity was created; receives the polymorphic Entity object (use :as_pawn()) plus its entry index. |
| `on_entity_destroy` | `on_entity_destroy(entity: Entity\|nil, idx: integer)` | safe | Game thread. An entity is being destroyed; re-resolved while still live (nil if already gone) plus its entry index. |
| `on_sound` | `on_sound(name: string, x: number, y: number, z: number)` | safe | Game thread. A sound event played: sound name + world position. |
| `on_scripts_loaded` | `on_scripts_loaded()` | safe | Fires ONCE after every script has finished loading (boot). Build menus / register UI here. |
| `OnLoad` | `OnLoad()` | safe |  |
| `OnUnload` | `OnUnload()` | safe |  |
| `OnUpdate` | `OnUpdate()` | safe |  |
| `OnRender` | `OnRender()` | safe |  |

## Global constants

Enum ordinals + shared constant tables exposed at the top level.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Vector` | `.Vector: Vector3` | safe | Alias of Vector3 (LuaEntityAPI.cpp:186). |
| `ImColor` | `.ImColor: Color` | safe | Alias of Color. ImColor() with no arguments is opaque white. |
| `TargetSelection` | `.TargetSelection: lua_target_selection_wrapper_t` | safe | Factory alias of lua_target_selection_wrapper_t (LuaUsertypes.cpp:1981). |

---

_Generated from `src/data/lua_api.json`. Regenerate with `npm run gen-lua-api`._
