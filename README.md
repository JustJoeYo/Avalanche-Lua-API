# Avalanche Lua API

Flat, exhaustive reference of the **entire** Avalanche Lua scripting API.

> **Auto-generated — do not edit.** Derived from the in-game registry (`Avalanche LuaApiRegistry`, schema v1) via `npm run gen-lua-api`. For the full interactive docs (with prose walkthroughs, worked example scripts, and search) see **https://avalan.cc/developers/lua**.

**130** scopes · **4173** members · **76** globals · **61** callbacks · **3** constants

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
  - [Preview](#preview)
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
  - [hx_hud](#hx_hud)
  - [hx_util](#hx_util)
  - [hx_steps](#hx_steps)
  - [hx_opts](#hx_opts)
  - [hx_cfg](#hx_cfg)
  - [hx_charge](#hx_charge)
  - [hx_input](#hx_input)
  - [InputAcquire](#inputacquire)
  - [hx_target](#hx_target)
  - [hx_aim](#hx_aim)
  - [hx_vis](#hx_vis)
  - [hx_cast](#hx_cast)
  - [CastProjectile](#castprojectile)
  - [hx_registry](#hx_registry)
  - [RegistryCaller](#registrycaller)
  - [hx_bus](#hx_bus)
  - [hx_chess_board](#hx_chess_board)
  - [hx_blocks](#hx_blocks)
  - [hx_close_in](#hx_close_in)
  - [hx_items](#hx_items)
  - [hx_items_first](#hx_items_first)
  - [hx_feature_autocast](#hx_feature_autocast)
  - [hx_rook_flight](#hx_rook_flight)
  - [hx_feature_headlock](#hx_feature_headlock)
- [Global functions](#global-functions)
- [Callbacks](#callbacks)
- [Global constants](#global-constants)

## Scopes

### Vector3

`usertype` · tier `safe` — 3D vector (game world units).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `x` | `.x: number` | safe | X component (engine units). |
| `y` | `.y: number` | safe | Y component (engine units). |
| `z` | `.z: number` | safe | Z component (vertical, engine units). |
| `IsZero` | `:IsZero() -> boolean` | safe | True when x, y and z are all exactly 0. |
| `Length` | `:Length() -> number` | safe | Euclidean length, sqrt(x*x + y*y + z*z). |
| `length` | `:length() -> number` | safe | Euclidean length, sqrt(x*x + y*y + z*z) (snake_case alias of Length). |
| `length_2d` | `:length_2d() -> number` | safe | Horizontal length, sqrt(x*x + y*y); ignores z. |
| `length_sqr` | `:length_sqr() -> number` | safe | Squared length, x*x + y*y + z*z (skips the sqrt). |
| `dist` | `:dist(other: Vector3) -> number` | safe | Distance in game UNITS (same function as Distance). |
| `dist_2d` | `:dist_2d(other: Vector3) -> number` | safe | Horizontal (x, y) distance in game UNITS (same function as Distance2D). |
| `dot` | `:dot(other: Vector3) -> number` | safe | Dot product with another vector (a.x*b.x + a.y*b.y + a.z*b.z). |
| `cross` | `:cross(other: Vector3) -> Vector3` | safe | Cross product with another vector (right-hand rule). |
| `normalized` | `:normalized() -> Vector3` | safe | Unit-length copy; returns a zero vector when the input length is below 1e-6. |
| `lerp` | `:lerp(other: Vector3, t: number) -> Vector3` | safe | Component-wise linear interpolation toward `b` by `t` (not clamped). |
| `dir_to` | `:dir_to(other: Vector3) -> Vector3` | safe | Unit direction from self to `b`; returns a zero vector when the distance is below 1e-6. |
| `to_angles` | `:to_angles() -> table` | safe | Direction vector -> { pitch, yaw, roll }. |
| `Distance` | `:Distance(other: Vector3) -> number` | safe | Distance in game UNITS (Math.Distance returns meters). |
| `Distance2D` | `:Distance2D(other: Vector3) -> number` | safe | Horizontal (x, y) distance in game UNITS. |
| `Normalized` | `:Normalized() -> Vector3` | safe | Returns a unit-length copy; a zero-length vector returns the zero vector. |
| `ToScreen` | `:ToScreen() -> table\|nil` | safe | Projects the world-space vector onto the screen; returns `{x, y, visible=true}` on success, or nil if the point is not projectable. |
| `Cross` | `:Cross(b: Vector3) -> Vector3` | safe | Returns the cross product self x b. |
| `Dot` | `:Dot(other: Vector3) -> number` | safe | Returns the dot product of two vectors (binds to the free Dot helper). |
| `Length2D` | `:Length2D() -> number` | safe | Returns sqrt(x*x + y*y), ignoring the z component. |
| `LengthSqr` | `:LengthSqr() -> number` | safe | Squared length of the vector. |

### Vec2

`usertype` · tier `safe` — 2D vector.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `x` | `.x: number` | safe | X component. |
| `y` | `.y: number` | safe | Y component. |
| `Length` | `:Length() -> number` | safe | Vector magnitude. |
| `Distance` | `:Distance(other: Vec2) -> number` | safe | Distance to another Vec2. |
| `Normalized` | `:Normalized() -> Vec2` | safe | Unit-length copy (origin if zero-length). |

### Angle

`usertype` · tier `safe` — Euler angle (pitch, yaw, roll in degrees).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `pitch` | `.pitch: number` | safe | Pitch in degrees (vertical rotation; negative looks up). |
| `yaw` | `.yaw: number` | safe | Yaw in degrees (horizontal rotation around the Z axis). |
| `roll` | `.roll: number` | safe | Roll in degrees (bank rotation around the forward axis). |
| `Forward` | `:Forward() -> Vector3` | safe | Unit forward vector for this angle. |
| `Right` | `:Right() -> Vector3` | safe | Unit right vector for this angle. |
| `Up` | `:Up() -> Vector3` | safe | Unit up vector for this angle. |

### Color

`usertype` · tier `safe` — RGBA color. Construct via Color(r,g,b,a) or ImColor(...).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `r` | `.r: number` | safe | Red channel (0–255). |
| `g` | `.g: number` | safe | Green channel (0–255). |
| `b` | `.b: number` | safe | Blue channel (0–255). |
| `a` | `.a: number` | safe | Alpha channel (0–255). |
| `with_alpha` | `:with_alpha(a: integer) -> Color` | safe | Copy with alpha replaced. |
| `scale_alpha` | `:scale_alpha(scale: number) -> Color` | safe | Copy with alpha multiplied by scale. |
| `lerp` | `:lerp(other: Color, t: number) -> Color` | safe | Component-wise lerp toward other (t clamped 0..1). |
| `to_hex` | `:to_hex() -> string` | safe | "#RRGGBBAA" hex string. |
| `luminance` | `:luminance() -> number` | safe | Perceptual luminance (0.299r + 0.587g + 0.114b). |
| `to_argb` | `:to_argb() -> integer` | safe | Packs the color as a 32-bit 0xAARRGGBB integer. |
| `to_abgr` | `:to_abgr() -> integer` | safe | Packs the color into an ABGR 32-bit integer. |

### Ability

`usertype` · tier `safe` — Citadel ability handle (upgrade-aware, identity-revalidated). `a == b` is true for two handles of the same game instance.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe | True if the ability pointer is live (alive-check against the entity frame). |
| `get_name` | `:get_name() -> string` | safe | Returns the ability entity's classname string (m_iszClassname); empty when the ability is not alive. |
| `get_class_name` | `:get_class_name() -> string` | safe | Returns the ability's schema class name; empty string when the ability is not alive. |
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
| `get_level` | `:get_level() -> integer` | safe | Returns the upgrade level (0-3) decoded from the packed m_nUpgradeInfo bits; -1 when the ability is not alive. |
| `get_target` | `:get_target() -> PlayerPawn\|nil` | safe | Returns the ability's current target entity (PlayerPawn for pawns, otherwise base entity) resolved through its target handle; nil when there is no live target. |
| `get_upgrades` | `:get_upgrades() -> table\|nil` | safe | Returns a table { level, bits, packed, max } describing the ability's upgrade state and max level from CitadelAbilityVData.m_iMaxLevel. |
| `get_upgrade` | `:get_upgrade(level: integer) -> boolean` | safe | True when the ability's decoded upgrade level is at or above the given level. |
| `find_entities_in_cone` | `:find_entities_in_cone(range: number, angle_deg: number) -> PlayerPawn[]` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_imbued_abilities` | `:get_imbued_abilities() -> table` | safe | Abilities this item has imbued (items with an imbue target only, e.g. Echo Shard, Mystic Reverb). Matched by the ability's subclass identity (m_nSubclassID). |
| `has_imbue_for` | `:has_imbue_for(...: any) -> boolean` | safe | True if this item has imbued the given ability. Accepts an Ability, a subclass token, or an ability class name. |
| `get_raw_vdata` | `:get_raw_vdata() -> raw_struct\|nil` | privileged | Raw memory view of the ability's CitadelAbilityVData (chain: CitadelAbilityVData, CEntitySubclassVDataBase); nil without the raw-read capability or when the ability or vdata is missing. |
| `get_raw_struct` | `:get_raw_struct() -> raw_struct\|nil` | privileged | Raw memory view of the ability instance (binding class, C_CitadelBaseAbility, C_BaseEntity, CEntityInstance chain); nil without the raw-read capability or when the ability is not alive. |
| `get_vdata` | `:get_vdata() -> table\|nil` | safe | A read-only schema view of the ability's vdata: fields by schema name, embedded classes as nested views (vdata.m_projectileInfo.m_flSpeed, vdata.m_eAbilityActivation). No address and no writers, so it is not gated like raw_struct. A view kept past a map change reads whatever lives there now; ask again rather than keep one. nil without vdata. |
| `is_on_cooldown` | `:is_on_cooldown() -> boolean` | safe | True when the ability's remaining cooldown (av::combo::ability_cooldown_remaining) is greater than zero. |
| `cooldown` | `:cooldown() -> number` | safe | Seconds of cooldown remaining on this ability (av::combo::ability_cooldown_remaining); 0 when the ability is not alive. |
| `can_be_executed` | `:can_be_executed() -> integer` | safe | Returns 1 when av::combo::is_ability_ready reports the ability as ready to cast, otherwise 0. |
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
| `get_handle` | `:get_handle() -> integer\|nil` | safe | The packed entity handle, the number entity:get_handle() returns; nil when the ability is not live. |
| `get_weapon_info` | `:get_weapon_info() -> table\|nil` | safe | The authored bullet data of the ability's weapon info (the "primary" entry of its vdata's m_mapWeaponInfos) as a fresh table; each key is present only when this build's schema declares its field: bullet_speed (units/s), bullet_gravity (m_flBulletGravityScale x sv_gravity), bullet_gravity_scale, bullet_lifetime (s), radius (vs entities), radius_vs_world, cycle_time (s), damage, range, vertical_aim_bias. nil without weapon info. |
| `get_alt_cast_hold_start_time` | `:get_alt_cast_hold_start_time() -> number` | safe | Game time the alt-cast (self-cast) hold began; 0 while none is in progress. |
| `get_alt_cast_doubletap_start_time` | `:get_alt_cast_doubletap_start_time() -> number` | safe | Game time the alt-cast double tap began; 0 while none is in progress. |
| `get_stolen_slot` | `:get_stolen_slot() -> integer\|nil` | safe | For an ability Sinclair has actively stolen: the slot it was stolen from (m_eStolenInSlot.m_eStolenSlot, 0-based like get_slot). nil when it is not actively stolen. |
| `get_cast_delay_start_time` | `:get_cast_delay_start_time() -> number` | safe | Game time when the current cast-delay began (`m_flCastDelayStartTime`); 0 when the ability is not alive. |
| `is_channeling` | `:is_channeling() -> boolean` | safe | True while the ability is currently channeling (`m_bChanneling`); false when the ability is not alive. |
| `get_cast_mode` | `:get_cast_mode() -> string` | safe | Returns `"confirm"`, `"release"`, or `"instant"` based on `av::combo::ability_cast_mode`; empty string if the ability is not alive. |
| `is_selected` | `:is_selected() -> boolean` | safe | Returns true when the ability is alive and `av::combo::is_ability_selected` reports it as the currently selected ability. |
| `as_bull_charge` | `:as_bull_charge() -> Ability_BullCharge\|nil` | safe | Casts the ability to the Bull Charge subclass; returns nil when the ability is dead or not of that kind. |
| `get_cast_start_time` | `:get_cast_start_time() -> number` | safe | Returns the ability's cast start game time; 0 when the ability is not alive. |
| `is_valid` | `:is_valid() -> boolean` | safe | Alias of `Ability.valid`; returns true when the ability pointer is still alive. |
| `as_entity` | `:as_entity() -> Entity` | safe | Reinterprets the ability as a `C_BaseEntity` without validity checks. |
| `get_channel_start_time` | `:get_channel_start_time() -> number` | safe | Returns `m_flChannelStartTime`, or 0 when the ability isn't alive. |
| `selection_mode_is_alt` | `:selection_mode_is_alt() -> boolean` | safe | True when `m_bSelectionModeIsAltMode` is set on a live ability. |
| `as_fealty` | `:as_fealty() -> Ability_Fealty\|nil` | safe | Returns self as an Ability_Fealty when the ability's kind is Fealty, otherwise nil. |
| `get_charge_recharge_end` | `:get_charge_recharge_end() -> number` | safe | Returns m_flChargeRechargeEnd, or 0 when the ability is not alive. |
| `should_be_executed` | `:should_be_executed() -> boolean` | safe | Returns m_bShouldBeExecuted, or false when the ability is not alive. |
| `as_flying_strike` | `:as_flying_strike() -> Ability_FlyingStrike\|nil` | safe | Narrows the ability to Ability_FlyingStrike when it is alive and its KindOf is FlyingStrike; otherwise returns nil. |
| `get_charge_recharge_start` | `:get_charge_recharge_start() -> number` | safe | Returns the game-time at which the next charge began recharging (m_flChargeRechargeStart); 0 when the ability is not alive. |
| `as_tango_tether` | `:as_tango_tether() -> Ability_TangoTether\|nil` | safe | Casts this ability to its Tango-Tether subtype; returns nil when the ability is dead or not of that kind. |
| `get_index` | `:get_index() -> integer` | safe | Returns the ability entity's index via `GetEntityIndex()`; 0 when the ability is dead. |
| `as_ult_combo` | `:as_ult_combo() -> Ability_UltCombo\|nil` | safe | Downcast to the UltCombo subclass handle, or nil if the ability is dead or not of kind `UltCombo`. |
| `get_movement_control_active_time` | `:get_movement_control_active_time() -> number` | safe | Reads `m_flMovementControlActiveTime`; 0 when the ability is not alive. |
| `can_cast` | `:can_cast() -> boolean` | safe | True when the ability is alive, ready (combo::is_ability_ready) and currently activatable (combo::can_activate_ability). |
| `get_owner_handle` | `:get_owner_handle() -> CHandle` | safe | Returns the m_hOwnerEntity handle of the ability's backing entity, or an invalid CHandle if the ability is not alive. |
| `get_ability_type` | `:get_ability_type() -> integer` | safe | Returns the ability's `m_eAbilityType` enum value; -1 when the ability is dead or has no vdata. |
| `get_post_cast_delay_end_time` | `:get_post_cast_delay_end_time() -> number` | safe | Returns `m_flPostCastDelayEndTime`; 0 when the ability is dead. |
| `get_cast_point` | `:get_cast_point() -> number` | safe | Returns the ability's computed cast delay in seconds, or 0 when the ability is not alive. |
| `can_be_imbued` | `:can_be_imbued() -> boolean` | safe | Reads the ability's `m_bCanBeImbued` schema field; false when the ability is not alive. |
| `get_remaining_charges` | `:get_remaining_charges() -> integer` | safe | Returns `m_iRemainingCharges`, or 0 when the ability is not alive. |
| `get_image_path` | `:get_image_path() -> string` | safe | Returns the VData `m_strAbilityImage.szImagePath`, or an empty string when the ability or its VData is missing. |
| `can_be_upgraded` | `:can_be_upgraded() -> boolean` | safe | Reads `m_bCanBeUpgraded` from the ability; false if it is not alive. |
| `get_selected_changed_time` | `:get_selected_changed_time() -> number` | safe | Returns `m_flSelectedChangedTime`, or 0 if the ability is not alive. |
| `get_projectile_speed` | `:get_projectile_speed() -> number` | safe | Returns the ability's projectile speed via `GetProjectileSpeed()`, or 0 when the ability is not alive. |
| `get_ability_index` | `:get_ability_index() -> integer` | safe | Returns `GetAbilityIndex()`, or 0 when the ability is not alive. |
| `get_toggle_state` | `:get_toggle_state() -> boolean` | safe | Returns `m_bToggleState`, or false when the ability is not alive. |
| `get_target_handle` | `:get_target_handle() -> any` | safe | Returns the ability's current target CHandle; empty handle when the ability is not alive. |
| `get_address` | `:get_address() -> integer\|nil` | safe | Returns the ability's raw pointer as a 64-bit integer; nil when the raw-read capability is not allowed. |
| `get_upgrade_bits` | `:get_upgrade_bits() -> integer` | safe | Returns the upgrade bitmask from the ability's packed upgrade info; 0 if the ability is not alive. |
| `get_vdata_ptr` | `:get_vdata_ptr() -> integer\|nil` | safe | Returns the address of the ability's CitadelAbilityVData struct as an unsigned 64-bit integer, gated by the raw-read capability; returns nothing when the ability is not alive or the capability is denied. |
| `get_cast_buttons` | `:get_cast_buttons() -> integer,integer` | safe | Returns the ability's cast-button state as (held_mask, pressed_mask); both come back as 0 when the ability is not alive. |
| `get_upgrade_info` | `:get_upgrade_info() -> integer` | safe | Returns the packed upgrade-info integer for the ability (the raw bits backing level/upgrade queries), or 0 when the ability is not alive. |
| `has_property` | `:has_property(key: string) -> boolean` | safe | Checks whether the ability exposes the named property: schema fields prefixed with `m_`, the special keys `cast_range`/`aoe_radius`/`projectile_speed`, or an authored VData property; false when the ability is dead or the key is empty. |
| `get_cast_completed_time` | `:get_cast_completed_time() -> number` | safe | `m_flCastCompletedTime`; 0 if the ability is dead. |
| `in_cast_delay` | `:in_cast_delay() -> boolean` | safe | `m_bInCastDelay`; false if the ability is dead. |

### PlayerPawn

`usertype` · tier `safe` — Citadel player pawn (hero entity). Its scalar reads (team, health, alive, flags, velocity, dormancy, eye and view, relation, modifier states, hero / steam id / name) come from the per-tick entity frame and can lag the live pawn by up to one tick; in render callbacks get_origin / get_abs_origin / distance_to* are this frame's drawn position once the pawn is drawn. `a == b` is true for two handles of the same game instance.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe | True if the pawn pointer is in the current entity frame or passes the live alive-check. |
| `is_alive` | `:is_alive() -> boolean` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_origin` | `:get_origin() -> Vector3` | safe | On the game thread, the per-tick origin: the same value for the whole tick, and the same value HERO_LIB.get_origin returns; use it there for tick-consistent math. Off the game thread (render callbacks), the live interpolated origin of the same pawn, so a world-to-screen does not lag a tick. (0,0,0) for a stale pawn. |
| `get_velocity` | `:get_velocity() -> Vector3` | safe | Networked velocity (units/s) from the tick snapshot (can lag one tick). |
| `get_name` | `:get_name() -> string` | safe | Returns the pawn entity's classname string (m_iszClassname); empty when the pawn is not alive. |
| `get_handle` | `:get_handle() -> integer\|nil` | safe | Full raw CHandle value (entry index + SERIAL bits); nil when the pawn is not live. Identical in meaning to Entity:get_handle(). Use this as a cache key when you need ENTITY IDENTITY: because it carries the serial, a recycled entry slot produces a DIFFERENT key (a cache miss) instead of silently hitting the dead occupant's entry. CHANGED: this previously returned the bare entry index (no serial) and 0 when not live -- so `if not h` never fired (0 is truthy in Lua) and recycled slots caused wrong cache hits. If you want the bare slot, use get_index(). |
| `get_index` | `:get_index() -> integer` | safe | Entity ENTRY index (bare slot, NO serial bits). The right key for a cache that means "this slot" and does not need entity identity; for an identity-stable key use get_handle(). Unchanged. |
| `get_vdata_class_name` | `:get_vdata_class_name() -> string` | safe | Returns the pawn's schema class name; empty string when the pawn is not alive. |
| `get_health` | `:get_health() -> number` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_max_health` | `:get_max_health() -> number` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_scaling_stat` | `:get_scaling_stat(stat_type: integer) -> number` | safe | Returns the live value for the given stat id via av::sdk::GetEntityStat on the pawn; game-thread only, 0 otherwise. |
| `get_starting_stat` | `:get_starting_stat(stat_type: integer) -> number` | safe | Returns the live value for the given stat id via av::sdk::GetEntityStat on the pawn (same read path as get_scaling_stat); game-thread only, 0 otherwise. |
| `get_modifier_value` | `:get_modifier_value(mod_type: integer, default_value?: number) -> number` | safe | mod_type is an EModifierValue number (the EModifierValue / ModifierValue tables; never a literal). Tech power, max health and bullet / tech resist answer the live stat; every other value is the sum of the pawn's enabled modifiers' scripted values plus their abilities' tagged properties. default_value (0) when nothing provides the value or off the game thread. CHANGED: it used to answer only the four stat-backed values and the ModifierValue numbers were made up (see ModifierValue). |
| `get_sum_modifier_value` | `:get_sum_modifier_value(mod_type: integer, default_value?: number) -> number` | safe | Same answer as get_modifier_value. mod_type is an EModifierValue number (the EModifierValue / ModifierValue tables; never a literal). Tech power, max health and bullet / tech resist answer the live stat; every other value is the sum of the pawn's enabled modifiers' scripted values plus their abilities' tagged properties. default_value (0) when nothing provides the value or off the game thread. CHANGED: it used to answer only the four stat-backed values and the ModifierValue numbers were made up (see ModifierValue). |
| `can_be_lasthitted` | `:can_be_lasthitted(...: any) -> boolean` | safe | True when herolib::CanBeLastHitted reports the pawn as last-hittable; the first vararg, if a boolean, is forwarded as the strict flag. |
| `get_team` | `:get_team() -> integer` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_class_name` | `:get_class_name() -> string` | safe | Returns the pawn entity's classname string (m_iszClassname); empty when the pawn is not alive. |
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
| `get_trace` | `:get_trace(...: any) -> Vector3\|nil` | safe | Stub that always returns nil; retained for compatibility with older scripts. |
| `get_attachment` | `:get_attachment(name: string) -> Vector3\|nil` | safe | Resolves a named model attachment and returns its world-space Vector3 position; defaults to "ability_cast" when the name is empty, and returns nil if the attachment is missing or produces non-finite coordinates. |
| `is_visible` | `:is_visible() -> boolean` | safe | Traced line of sight from the local eye, from the tick snapshot; an ally's value can be up to 3 ticks old. |
| `has_modifier_state` | `:has_modifier_state(state: integer) -> boolean` | safe | Modifier-state bit from the tick snapshot (can lag one tick); a dead or dormant pawn reads all clear. |
| `has_modifier` | `:has_modifier(name: string) -> boolean` | safe | True when the pawn has a modifier whose name matches the given string (AV_HasEntityModifier lookup). |
| `matches_predicates` | `:matches_predicates(...: string\|integer) -> boolean` | safe | Every argument must hold. A string is a comma-separated slug list in the shared pred:/group:/state:/mod:/flag: vocabulary and holds if ANY slug matches; an integer is an EModifierState ordinal that must be enabled. A mod: slug containing '/' is an exact (case-insensitive) modifier name; a bare fragment is a substring. CHANGED: string arguments used to always return false. |
| `has_particle` | `:has_particle(path: string) -> boolean` | safe | True when the pawn's recent particle list contains an entry matching the given path substring (AV_HasParticleMatch). |
| `has_any_particle` | `:has_any_particle(...: string\|string[]) -> boolean` | safe | Any substring matches a particle recently created on this pawn. Accepts EITHER varargs strings `has_any_particle("a","b")` OR an array table `has_any_particle({"a","b"})` — both shapes work on every has_any_particle binding. No args => any recent particle at all. For anything TIMING-sensitive use get_particle_age instead: this stays true for the tracker's full 3s TTL. |
| `get_particle_age` | `:get_particle_age(...: string\|string[]) -> number\|nil` | safe | Seconds since the FRESHEST matching particle was created on this pawn, or nil if none is within the tracker's ~3s TTL. No args => age of the most recent particle of any path. Use this over has_any_particle whenever the question is a timing one (e.g. 'is this windup still live?'), since the boolean cannot distinguish a charge starting now from one that finished 3 seconds ago. |
| `get_abilities` | `:get_abilities() -> Ability[]` | safe | Returns a 1-indexed table of every C_CitadelBaseAbility currently owned by the pawn (ForEachAbility walk); empty when the pawn is not alive. |
| `get_ability` | `:get_ability(name_or_slot: string\|integer) -> Ability\|nil` | safe | A string resolves an ability by class name (FUZZY substring match — e.g. "citadel_ability_melee" also matches CCitadel_Ability_MeleeParry). An integer is an EAbilitySlots_t slot, same as get_ability_by_slot. For items use HERO_LIB.owned_item(record name): an item's class name is its vdata _class, which many items share. |
| `get_ability_exact` | `:get_ability_exact(class: string) -> Ability\|nil` | safe | Resolve an ability by EXACT binding-class name (byte-for-byte), avoiding get_ability's fuzzy substring match. |
| `get_ability_by_slot` | `:get_ability_by_slot(slot: integer) -> Ability\|nil` | safe | The ability the game put in this EAbilitySlots_t slot (matched on m_eAbilitySlot): signatures 0..3, active items 4..7, primary weapon 21. nil outside 0..22 or when the slot is empty. CHANGED: used to index the ability vector, whose order is not the slot order. |
| `get_signature_ability` | `:get_signature_ability(index: integer) -> Ability\|nil` | safe | Signature ability by 0-based index (0..3 = ability 1..4), resolved by slot. The index is clamped to 0..3. |
| `get_item` | `:get_item(index: integer) -> Ability\|nil` | safe | Active item by 0-based index (0..3 = item slots 4..7), resolved by slot. nil outside 0..3. |
| `get_items` | `:get_items() -> Ability[]` | safe | Every ability whose vdata type is Item, passive items included, in the pawn's ability-vector order. |
| `get_weapon` | `:get_weapon() -> Ability\|nil` | safe | The primary weapon (slot 21). Same as get_primary_weapon. |
| `get_bone_position` | `:get_bone_position(bone: string\|integer) -> Vector3` | safe | Bone position by name (the same source as get_bone_pos, so (0,0,0) in render callbacks until the pawn is in the screen frame) OR by integer index into the resolved-bone list (a skeleton solve). Returns Vector3(0,0,0) on unknown name, out-of-range index, non-finite result, or dormant pawn. `get_bone_pos(name)` remains as a name-only convenience. |
| `get_modifiers` | `:get_modifiers() -> Modifier[]` | safe | Returns a 1-indexed table of every modifier currently applied to the pawn (WalkEntityModifiers); empty when the pawn is not alive. |
| `get_modifier` | `:get_modifier(name: string) -> Modifier\|nil` | safe | Returns the modifier on the pawn whose name matches the given string, or nil when no match is found. |
| `is_dormant` | `:is_dormant() -> boolean` | safe | Tick snapshot: can lag the live entity by up to one tick. |
| `get_address` | `:get_address() -> integer` | safe | Returns the pawn's raw pointer as an integer; nil without the raw-read capability. |
| `get_angles` | `:get_angles() -> Vector3` | safe | Eye angles from the tick snapshot (can lag one tick). |
| `get_primary_weapon` | `:get_primary_weapon() -> Ability\|nil` | safe | The ability in the primary-weapon slot (21). CHANGED: used to return the first ability-vector entry. |
| `get_currency` | `:get_currency(...: any) -> integer` | safe | Returns the pawn's currency amount at the index given by the first vararg (defaults to 0, i.e. souls). |
| `get_account_id` | `:get_account_id() -> integer` | safe | The controlling player's 64-bit Steam id (m_steamID), from the controller's row in the tick snapshot (can lag one tick), else a live controller read. 0 if no controller owns this pawn. |
| `get_hero_id` | `:get_hero_id() -> integer` | safe | Raw hero id of the controlling player, from the controller's row in the tick snapshot (can lag one tick), else a live controller read. 0 if no controller owns this pawn. |
| `get_hero_name` | `:get_hero_name() -> string` | safe | Hero name for get_hero_id (same source, can lag one tick). "" if no controller owns this pawn. |
| `get_vdata` | `:get_vdata() -> raw_struct\|nil` | privileged | Returns a raw-struct view over the pawn for schema-field access. |
| `get_bones` | `:get_bones() -> table` | safe | Returns a 1-indexed table of up to 256 bone entries, each a table with `index` and `position` (world-space Vector3) read from the pawn's skeleton. |
| `get_skeleton_instance` | `:get_skeleton_instance() -> integer` | privileged | Returns the pawn's CSkeletonInstance (through its scene node), or nil when unavailable. |
| `get_min_fov_to_bones` | `:get_min_fov_to_bones(cam: Vector3, yaw_only?: boolean) -> number` | safe | Returns the smallest angular distance (degrees) between the given view (position + yaw/pitch encoded in x/y) and any of the pawn's bones; 180 when the pawn is not alive. |
| `get_fireport_position` | `:get_fireport_position() -> Vector3` | safe | Returns the world-space position of the pawn's `muzzle_fx` attachment, falling back to its eye position when the attachment is missing or non-finite. |
| `get_model_name` | `:get_model_name() -> string` | safe | Returns the model path currently bound to the pawn's skeleton (m_modelState.m_ModelName); empty when the pawn is not alive or the model is unresolved. |
| `get_particles` | `:get_particles() -> string[]` | safe | DISTINCT particle paths recently created on this pawn (within the tracker's ~3s TTL), oldest first. A path that re-spawns is refreshed in place rather than duplicated, so this lists what is recently live — not a spawn log. Empty if none / not live. |
| `get_particle_position` | `:get_particle_position(...: any) -> Vector3\|nil` | safe | Stub that always returns nil; retained for compatibility with older scripts. |
| `get_hitboxes` | `:get_hitboxes() -> table[]` | safe | Per-hitbox list: { center, bone_pos, mins, maxs, radius, capsule_a, capsule_b, capsule_radius, bone_index, shape } (no name field). From this tick's aim set: {} for a pawn outside it, which joins from the next tick while scripts ask (allies included). Always {} for the local pawn. |
| `get_bbox` | `:get_bbox() -> table\|nil` | safe | Axis-aligned bounding box { mins, maxs } (plus world / screen sub-tables). |
| `get_bounding_box` | `:get_bounding_box() -> table\|nil` | safe | Native screen-space bounding rect { x, y, w, h } (C_BaseModelEntity::GetBoundingBox) - NOT the same as get_bbox. |
| `closest_hitbox_point_to_ray` | `:closest_hitbox_point_to_ray(origin: Vector3, dir: Vector3) -> table\|nil` | safe | Closest hitbox-surface point to a ray, over the same hitboxes as get_hitboxes: nil for a pawn outside this tick's aim set, and always nil for the local pawn. |
| `set_glow` | `:set_glow(color: Color, mode?: number, width?: number) -> boolean` | safe | Enable entity glow (see GlowMode). |
| `clear_glow` | `:clear_glow() -> boolean` | safe | Disable entity glow. |
| `get_player_name` | `:get_player_name() -> string` | safe | Display name of the controlling player, from the controller's row in the tick snapshot (can lag one tick), else a live controller read; "" if no controller owns this pawn (e.g. a target dummy) or not live. |
| `get_controller` | `:get_controller() -> Entity\|nil` | safe | This pawn's owning CCitadelPlayerController as a generic Entity (read any controller schema field / :get_raw_struct); nil if none or not live. |
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
| `get_armor` | `:get_armor() -> number` | safe | Stub returning -1 — Deadlock exposes no direct armor stat on pawns. |
| `is_unstoppable` | `:is_unstoppable() -> boolean` | safe | True when the pawn is alive and the combat layer marks it as unstoppable (immune to hard CC). |
| `get_eye_pos` | `:get_eye_pos() -> Vector3` | safe | Alias of `get_eye_position` — world-space camera/eye origin for this pawn. |
| `get_team_number` | `:get_team_number() -> integer` | safe | Alias of `get_team` — team number of the pawn. |
| `get_modifier_property` | `:get_modifier_property() -> ModifierProperty\|nil` | safe | Returns the pawn's `CModifierProperty` container; nil if the pawn is not alive. |
| `modifier_count` | `:modifier_count() -> integer` | safe | Returns the number of modifiers currently attached to the pawn; 0 if the pawn is not alive. |
| `get_eye_position` | `:get_eye_position() -> Vector3` | safe | Returns the pawn's eye position via `LuaEyePosition`. |
| `get_view_angles` | `:get_view_angles() -> Angle` | safe | Alias of `PlayerPawn.get_eye_angles`. |
| `get_shields` | `:get_shields() -> number` | safe | Stub: always returns -1 (shields are not exposed on this pawn surface). |
| `get_flags` | `:get_flags() -> integer` | safe | Returns the pawn's engine flags bitmask. |
| `get_view_direction` | `:get_view_direction() -> Vector3` | safe | Returns the forward unit vector derived from the pawn's eye angles. |
| `has_ability` | `:has_ability(name: string) -> boolean` | safe | True when the pawn has an ability whose class name matches `name`. |
| `get_head_position` | `:get_head_position() -> Vector3` | safe | Returns the pawn's eye position (the head position used for view-ray math). |
| `has_incoming_ability` | `:has_incoming_ability() -> boolean` | safe | Stub that always returns false. |
| `is_asleep` | `:is_asleep() -> boolean` | safe | True when the pawn is alive and currently asleep (combo helper). |
| `get_last_input_vector` | `:get_last_input_vector() -> Vector3` | safe | Returns the pawn's last input vector, or a zero vector when the pawn is not alive. |
| `is_ally` | `:is_ally() -> boolean` | safe | True when the pawn is alive and its relation to the local pawn is Ally. |
| `is_busy_with_action` | `:is_busy_with_action(checking_item: boolean\|nil) -> boolean` | safe | Returns true when the pawn is alive and currently busy with a cast/ability action; checking_item (default false) extends the busy test to item casts. |
| `get_life_state` | `:get_life_state() -> integer` | safe | Returns the pawn's life state code (0 == alive, non-zero == dying/dead variants). |
| `is_bot` | `:is_bot() -> boolean` | safe | Returns true when the pawn's controller is a bot (checked via SteamID). |
| `is_casting` | `:is_casting() -> boolean` | safe | Returns true when any of the pawn's abilities currently has `m_bInCastDelay` set. |
| `get_max_move_speed` | `:get_max_move_speed() -> number` | safe | Returns `GetMaxMoveSpeed()`; 0 when the pawn is dead. |
| `is_enemy` | `:is_enemy() -> boolean` | safe | Returns true when the pawn is alive and on an opposing team relative to the local player. |
| `is_channeling` | `:is_channeling() -> boolean` | safe | True if any of the pawn's abilities has `m_bChanneling` set; false if the pawn is not alive. |
| `get_movement_services` | `:get_movement_services() -> nil` | safe | Stub that always returns nil; the movement-services service is not exposed. |
| `is_hero` | `:is_hero() -> boolean` | safe | True if the pawn is a live Citadel player pawn whose resolved hero id is non-zero. |
| `bone_count` | `:bone_count() -> integer` | safe | Returns CL_Bones' bone count for the pawn, or 0 if the pawn is not alive. |
| `is_disarmed` | `:is_disarmed() -> boolean` | safe | True when the pawn is alive and currently has the Disarmed modifier state set. |
| `as_base_pawn` | `:as_base_pawn() -> Entity` | safe | Reinterprets the Citadel player pawn as the base `C_BasePlayerPawn` usertype without a liveness check. |
| `get_observer_mode` | `:get_observer_mode() -> integer` | safe | Stub returning 0; observer-services queries are not wired through this surface. |
| `is_local` | `:is_local() -> boolean` | safe | True when the pawn is alive and matches the tracked local pawn. |
| `get_body_component` | `:get_body_component() -> any` | safe | Returns the pawn's `CBodyComponent`; nil when the pawn is not alive. |
| `is_hard_ccd` | `:is_hard_ccd() -> boolean` | safe | True while the pawn is alive and `av::combo::is_hard_ccd` reports hard crowd-control. |
| `as_entity` | `:as_entity() -> Entity` | safe | Reinterprets the pawn pointer as its `C_BaseEntity` base. |
| `get_observer_services` | `:get_observer_services() -> any` | safe | Stub that always returns nil; the observer-services pointer is not exposed from Lua. |
| `is_pawn` | `:is_pawn() -> boolean` | safe | True while `AlivePawn(self)` holds. |
| `get_bone_index` | `:get_bone_index(name: string) -> integer` | safe | Resolves a bone name on the pawn's skeleton to its index; returns -1 for a dead pawn or empty name. |
| `is_invisible_to_enemy` | `:is_invisible_to_enemy() -> boolean` | safe | True when the pawn is currently invisible to enemy sight; false when the pawn is not alive. |
| `distance_to` | `:distance_to(other: PlayerPawn) -> number` | safe | Returns the 3D distance between the two pawns' origins, or 0 when either is not alive. |
| `get_observer_target` | `:get_observer_target() -> integer` | safe | Service stub: always returns an invalid entity handle. |
| `is_player` | `:is_player() -> boolean` | safe | True when the pawn is alive and reports itself as a Citadel player pawn. |
| `get_bone_name` | `:get_bone_name(bone: integer) -> string` | safe | Returns the name of bone index `bone` on this pawn, or an empty string if the pawn is not alive. |
| `is_invulnerable` | `:is_invulnerable() -> boolean` | safe | Returns whether the pawn is currently invulnerable. |
| `distance_to_point` | `:distance_to_point(pt: Vector3) -> number` | safe | Returns the 3D distance from the pawn's origin to `pt`, or 0 if the pawn is not alive. |
| `get_owner_handle` | `:get_owner_handle() -> integer` | safe | Returns the pawn's `m_hOwnerEntity`, or an invalid handle if the pawn is not alive. |
| `is_teammate` | `:is_teammate() -> boolean` | safe | Returns true if the pawn's relation to the local pawn is friendly. |
| `get_glow` | `:get_glow() -> GlowProperty\|nil` | safe | Returns the pawn's glow-property pointer, or nil when the pawn is not alive. |
| `is_muted` | `:is_muted() -> boolean` | safe | Returns true when the pawn is currently in the Muted CC state. |
| `get_abs_origin` | `:get_abs_origin() -> Vector3` | safe | Returns the pawn's absolute origin (identical to `get_origin`); zero vector when the pawn is not alive. |
| `get_punch_angle` | `:get_punch_angle() -> Angle` | safe | Stub that always returns a zero QAngle. |
| `is_valid` | `:is_valid() -> boolean` | safe | Returns true when the pawn is either alive or still visible in the current frame snapshot. |
| `get_scene_node` | `:get_scene_node() -> any` | safe | Returns the pawn's CGameSceneNode; nil when the pawn is not alive. |
| `is_rooted` | `:is_rooted() -> boolean` | safe | Returns true if the pawn is alive and carries the Immobilized modifier state. |
| `get_camera_services` | `:get_camera_services() -> any` | safe | Stub that always returns nil; camera-services access is not wired for Lua. |
| `get_raw_struct` | `:get_raw_struct() -> any` | safe | Returns a raw_struct wrapper bound to this pawn's address and schema class chain. |
| `get_skeleton` | `:get_skeleton() -> SkeletonInstance\|nil` | safe | Returns the pawn's typed skeleton instance (via its scene node's `GetTypedSkeletonInstance`), or nil when the pawn or its scene node is not available. |
| `is_silenced` | `:is_silenced() -> boolean` | safe | Returns true when the pawn is alive and `av::combo::is_silenced` holds. |
| `get_controller_handle` | `:get_controller_handle() -> integer` | safe | Returns the pawn's `m_hController` handle, or an empty handle when the pawn is not alive. |
| `get_speed` | `:get_speed() -> number` | safe | Returns the length of the pawn's current velocity vector (3D speed), or 0 when the pawn is not alive. |
| `get_ability_by_name` | `:get_ability_by_name(name: string) -> Ability\|nil` | safe | Returns the pawn's ability whose class name matches, or nil if none. |
| `is_stunned` | `:is_stunned() -> boolean` | safe | True when the pawn is alive and the combo helper reports it as stunned. |
| `get_eye_angles` | `:get_eye_angles() -> Angle` | safe | Eye angles of the pawn as a QAngle (pitch/yaw/roll). |
| `get_speed_2d` | `:get_speed_2d() -> number` | safe | Horizontal (XY) speed derived from the pawn's velocity vector. |

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
| `get_modifier_by_id` | `:get_modifier_by_id(id: integer) -> Modifier\|nil` | safe | The modifier whose runtime name has string token `id`, as PlayerPawn:get_modifier_by_id, for any entity (troopers' wave buffs included). Game thread. |
| `has_active_particle` | `:has_active_particle(path: string) -> boolean` | safe | An effect with exactly this path (any case) is alive on the entity: created and not yet stopped or released. Any thread. The first call after ~10 s with no particle query or handler sees the effects created from then on. |
| `get_collision_bounds` | `:get_collision_bounds() -> Vector3, Vector3\|nil` | safe | The entity-space collision box (mins, maxs): the frame's bounds row, else the live collision property. nil when the entity has none or an empty one. No screen projection (get_bbox has that). |
| `get_vdata` | `:get_vdata() -> table\|nil` | safe | A read-only schema view of the entity's subclass vdata (vdata.m_flVaultMiniGameTime); the vdata object's own class when the game names it, else "<binding>VData", else only the common fields. nil without vdata. PlayerPawn:get_vdata keeps its own meaning (raw_struct). |
| `IsCitadelPlayerPawn` | `IsCitadelPlayerPawn(ent: Entity) -> boolean` | safe | True if the first argument resolves to a live entity whose `IsCitadelPlayerPawn()` returns true. |
| `get_bone_pos` | `:get_bone_pos(name: string) -> Vector3\|nil` | safe | World-space position of the named bone on this entity; nil when the entity is dead, the name is empty, or the lookup returns zero. |
| `get_team` | `:get_team() -> integer` | safe | Team number of the entity (0 when nil/dead). |
| `is_projectile` | `:is_projectile() -> boolean` | safe | True when the entity's role is classified as a projectile. |
| `IsNPC` | `IsNPC(ent: Entity) -> boolean` | safe | Returns `ent->IsNPC()` on the live entity; false when the entity is missing or dead. |
| `get_designer_name` | `:get_designer_name() -> string` | safe | Returns the entity's designer name, falling back to its `m_iszClassname` when no designer name is set; empty string if the entity is not alive. |
| `get_team_number` | `:get_team_number() -> integer` | safe | Returns the entity's team index via `LuaTeam`. |
| `is_soul` | `:is_soul() -> boolean` | safe | Returns true when the entity's role is `ItemXP` (a soul pickup). |
| `IsPlayerPawn` | `IsPlayerPawn(ent: Entity) -> boolean` | safe | Returns true when `ent` is a player pawn; false if the entity is not live. |
| `get_flags` | `:get_flags() -> integer` | safe | Returns the entity's engine flags bitmask. |
| `get_trace` | `:get_trace() -> any` | safe | Stub: always returns nil (no trace surface exposed on the base entity). |
| `is_valid` | `:is_valid() -> boolean` | safe | Returns true when the entity pointer is in the current frame cache or still alive. |
| `get_glow` | `:get_glow() -> any` | safe | Returns the entity's `CGlowProperty*`, or nil when the entity isn't alive. |
| `get_vdata_class_name` | `:get_vdata_class_name() -> string` | safe | Returns the schema class name resolved from the entity's vdata, or `""` when not alive. |
| `modifier_count` | `:modifier_count() -> integer` | safe | Walks the entity's modifier list and returns how many are active; 0 when not alive. |
| `get_handle_index` | `:get_handle_index() -> integer` | safe | Returns the raw CHandle index of the entity; falls back to the Lua entity index when the identity or handle is missing. |
| `get_velocity` | `:get_velocity() -> Vector3` | safe | Returns the entity's velocity vector. |
| `get_health` | `:get_health() -> integer` | safe | Returns the entity's current health. |
| `has_modifier` | `:has_modifier(name: string) -> boolean` | safe | Returns true when the entity is alive and carries a modifier with that name; false for a nil or empty name. |
| `get_life_state` | `:get_life_state() -> integer` | safe | Returns the entity's `m_lifeState` value (0 = alive). |
| `has_modifier_state` | `:has_modifier_state(state: integer) -> boolean` | safe | Returns true when the given modifier-state bit is set on the entity; false when the entity is dead or `state` is out of range. |
| `get_max_health` | `:get_max_health() -> integer` | safe | Entity's maximum health value. |
| `is_ability` | `:is_ability() -> boolean` | safe | True if the entity is an ability instance. |
| `get_modifier` | `:get_modifier(name: string) -> Modifier\|nil` | safe | Returns the first modifier on the entity whose name matches, or nil if the entity is not alive, name is empty, or no match exists. |
| `is_alive` | `:is_alive() -> boolean` | safe | True when the entity passes the shared liveness check (LuaAlive). |
| `get_modifier_property` | `:get_modifier_property() -> any` | safe | Returns the entity's `CModifierProperty` component when the entity is alive, otherwise nil. |
| `is_citadel_player` | `:is_citadel_player() -> boolean` | safe | True when the entity is alive and `IsCitadelPlayerPawn()` holds. |
| `get_modifiers` | `:get_modifiers() -> table` | safe | Returns an array of the entity's active modifiers; empty when the entity is not alive. |
| `is_creep` | `:is_creep() -> boolean` | safe | True when the entity's role classifies as an NPC/creep. |
| `get_name` | `:get_name() -> string` | safe | Returns the entity's `m_iszClassname`, or an empty string if the entity is not alive or the string is invalid. |
| `is_deployable` | `:is_deployable() -> boolean` | safe | Returns true if the entity's role classifies as a deployable. |
| `as_ability` | `:as_ability() -> Ability\|nil` | safe | Reinterprets the entity as an Ability when `is_ability` would return true; nil otherwise. |
| `get_origin` | `:get_origin() -> Vector3` | safe | Returns the entity's origin (identical to `get_abs_origin`); zero vector when not alive. |
| `is_dormant` | `:is_dormant() -> boolean` | safe | Returns the dormancy flag; false when alive and non-dormant. |
| `GetHeroID` | `GetHeroID(ent: Entity) -> integer` | safe | If ent is a citadel player pawn, returns its hero id (local pawn uses the cached controller id); returns -1 otherwise or when the entity frame is unstable. |
| `get_abs_origin` | `:get_abs_origin() -> Vector3` | safe | Alias of `Entity.get_origin`; returns the entity's absolute origin via LuaOrigin. |
| `get_owner_handle` | `:get_owner_handle() -> any` | safe | Returns m_hOwnerEntity as a CHandle; empty handle when the entity is not alive. |
| `is_npc` | `:is_npc() -> boolean` | safe | Returns true if the entity is alive and reports IsNPC(). |
| `GetLocalController` | `GetLocalController() -> PlayerController\|nil` | safe | Returns the local `CCitadelPlayerController` (via `av::ef::LocalController()`), or nil when none is live. |
| `get_body_component` | `:get_body_component() -> BodyComponent\|nil` | safe | Returns the entity's `m_CBodyComponent`, or nil when the entity is not alive. |
| `get_scene_node` | `:get_scene_node() -> GameSceneNode\|nil` | safe | Returns the entity's `m_pGameSceneNode`, or nil when the entity is not alive. |
| `is_pawn` | `:is_pawn() -> boolean` | safe | Returns true when the entity is alive and `IsCitadelPlayerPawn()` holds. |
| `GetMoveSpeed` | `GetMoveSpeed(ent: Entity) -> number` | safe | Max move speed of the entity when it is a Citadel player pawn; 0 for anything else or when the live-entity check fails. |
| `get_bone_index` | `:get_bone_index(name: string) -> integer` | safe | Resolves a bone name to its index via the bone cache; -1 when the entity is dead or the name is empty. |
| `get_speed` | `:get_speed() -> number` | safe | Magnitude of the entity's velocity vector (3D speed). |
| `is_player` | `:is_player() -> boolean` | safe | True when the entity is any player pawn (base `PlayerPawn` or `CitadelPlayerPawn`). |

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
| `get_team` | `:get_team() -> integer` | safe | Team number read from the controller (0 when dead/nil). |
| `get_team_number` | `:get_team_number() -> integer` | safe | Returns the controller's team via `LuaTeam`. |
| `is_alive` | `:is_alive() -> boolean` | safe | Returns true when the controller's hero pawn exists and has positive health. |
| `is_bot` | `:is_bot() -> boolean` | safe | True when the controller's SteamID identifies a bot. |
| `get_address` | `:get_address() -> integer\|nil` | safe | Returns the controller's raw pointer address when the raw-read capability is allowed, otherwise nil. |
| `is_connected` | `:is_connected() -> boolean` | safe | True when the controller is alive and its m_iConnected state equals Connected; defaults to Connected if the schema offset is unresolved. |
| `get_assists` | `:get_assists() -> integer` | safe | Returns the controller's m_iPlayerAssists stat. |
| `is_local` | `:is_local() -> boolean` | safe | Returns true when this controller is the local player's controller. |
| `get_deaths` | `:get_deaths() -> integer` | safe | Reads the controller's `m_iDeaths` PDG field. |
| `is_valid` | `:is_valid() -> boolean` | safe | Returns true when the controller pointer is non-null and still alive. |
| `get_denies` | `:get_denies() -> integer` | safe | Reads the controller's `m_iDenies` stat via the PDG schema. |
| `valid` | `:valid() -> boolean` | safe | True while the controller pointer resolves to a live controller record. |
| `get_hero_name` | `:get_hero_name() -> string` | safe | Returns the HeroConfig display name for the controller's hero id, or empty string if the controller is not alive. |
| `get_hero_pawn` | `:get_hero_pawn() -> PlayerPawn` | safe | Returns the hero pawn resolved from this controller (same backing function as `get_pawn`). |
| `get_hero_pawn_handle` | `:get_hero_pawn_handle() -> integer` | safe | Returns the controller's `m_hHeroPawn` entity handle, or an invalid handle when the controller is not alive. |
| `get_kills` | `:get_kills() -> integer` | safe | Returns the controller's `m_iPlayerKills` (0 if the controller is not alive). |
| `get_last_hits` | `:get_last_hits() -> integer` | safe | Returns the controller's last-hit count (`m_iLastHits`). |
| `get_level` | `:get_level() -> integer` | safe | Returns the controller's m_iLevel schema field as an int. |
| `get_pawn` | `:get_pawn() -> PlayerPawn\|nil` | safe | Alias of `PlayerController.get_hero_pawn`: returns the controller's hero pawn, or nil when none is live. |
| `get_pawn_handle` | `:get_pawn_handle() -> CHandle` | safe | Alias of `PlayerController.get_hero_pawn_handle`. |

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
| `get_parent` | `:get_parent() -> Entity\|nil` | safe | Returns the entity that owns this modifier (nil when the modifier or its container is not alive). |
| `get_parent_container` | `:get_parent_container() -> ModifierProperty\|nil` | safe | Returns the owning `CModifierProperty` via `Parent()`; nil when the modifier is not alive. |
| `get_property` | `:get_property(name: string) -> number` | safe | Stub: always returns 0 (modifier property reads from Lua are not wired). |
| `get_serial_number` | `:get_serial_number() -> integer` | safe | Returns the modifier's `GetModifierID()`, or 0 when not alive. |
| `get_start_time` | `:get_start_time() -> number` | safe | Returns the modifier's start time, or 0 when the modifier is not alive. |
| `get_team` | `:get_team() -> integer` | safe | Returns the modifier's team number (m_iTeam); 0 when the modifier is not alive. |
| `get_think_interval` | `:get_think_interval() -> number` | safe | Returns `m_flThinkInterval`; 0 when the modifier is dead. |
| `get_time_scale` | `:get_time_scale() -> number` | safe | Reads `m_flTimeScale`; returns 1 when the modifier is not alive. |
| `has_property` | `:has_property(name: string) -> boolean` | safe | Stub that always returns false; modifier-property lookup is not exposed. |
| `is_in_aura_range` | `:is_in_aura_range() -> boolean` | safe | Returns `IsInAuraRange()` of the modifier; false when the modifier is not alive. |
| `is_valid` | `:is_valid() -> boolean` | safe | True when the modifier record is still live. |
| `get_address` | `:get_address() -> integer\|nil` | safe | Returns the modifier's raw pointer as a uint64, or nil without the raw-read capability. |
| `get_attributes` | `:get_attributes() -> integer` | safe | Returns the modifier's `m_iAttributes` bitfield as an int; 0 when the modifier is not alive. |
| `get_destroy_reason` | `:get_destroy_reason() -> integer` | safe | Returns m_eDestroyReason as an int; 0 if the modifier is not alive. |
| `get_modifier_id` | `:get_modifier_id() -> integer` | safe | Returns `GetModifierID()` for the modifier, or 0 when it is not alive. |
| `get_modifier_name` | `:get_modifier_name() -> string` | safe | Alias of `Modifier.get_name`. |

### UserCmd

`usertype` · tier `safe` — Per-tick user command passed to on_createmove.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ang_camera_angles` | `.ang_camera_angles: Angle` | safe | Read-only. Current camera angles (outer cmd.ang_camera_angles) sanitised to finite floats; zero Angle when the field is absent. |
| `orig_ang_camera_angles` | `.orig_ang_camera_angles: Angle` | safe | Read-only. The camera angles captured on CreateMove entry, before any feature or script wrote the command; falls back to the live ang_camera_angles when nothing was captured. |
| `orig_vec_camera_position` | `.orig_vec_camera_position: Vector3\|nil` | safe | Read-only. The camera position captured on CreateMove entry, before any write; falls back to the live vec_camera_position, nil when the outer cmd has none. |
| `button_state0` | `.button_state0: integer` | safe | The down-buttons word (cmd.button_states.buttonstate1). Read+write; the setter mirrors into base.buttons_pb and notes the injected press on the CL_Bypass path. |
| `button_state1` | `.button_state1: integer` | safe | The changed-buttons word (cmd.button_states.buttonstate2). Read+write; the setter mirrors into base.buttons_pb and notes the injected press on the CL_Bypass path. |
| `button_state2` | `.button_state2: integer` | safe | The wheel-buttons word (cmd.button_states.buttonstate3). Read+write; the setter mirrors into base.buttons_pb. |
| `forwardmove` | `.forwardmove: number` | safe | Forward move axis (base.forwardmove). Read+write. |
| `leftmove` | `.leftmove: number` | safe | Strafe (left) move axis (base.leftmove). Read+write. |
| `upmove` | `.upmove: number` | safe | Vertical move axis (base.upmove). Read+write. |
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
| `add_buttonstate1` | `:add_buttonstate1(bit: integer) -> nil` | safe | ORs `bit` into cmd.button_states.buttonstate1 (the down word), notes the press on the CL_Bypass path, and mirrors the result into base.buttons_pb.buttonstate1. |
| `add_buttonstate2` | `:add_buttonstate2(bit: integer) -> nil` | safe | ORs `bit` into cmd.button_states.buttonstate2 (the changed word), notes the press on the CL_Bypass path, and mirrors the result into base.buttons_pb.buttonstate2. |
| `add_buttonstate3` | `:add_buttonstate3(bit: integer) -> nil` | safe | ORs `bit` into cmd.button_states.buttonstate3 (the wheel word) and mirrors the result into base.buttons_pb.buttonstate3. |
| `clear_buttonstate1` | `:clear_buttonstate1(bit: integer) -> nil` | safe | Masks `bit` out of cmd.button_states.buttonstate1 (the down word) and mirrors the result into base.buttons_pb.buttonstate1. |
| `clear_buttonstate2` | `:clear_buttonstate2(bit: integer) -> nil` | safe | Masks `bit` out of cmd.button_states.buttonstate2 (the changed word) and mirrors the result into base.buttons_pb.buttonstate2. |
| `clear_buttonstate3` | `:clear_buttonstate3(bit: integer) -> nil` | safe | Masks `bit` out of cmd.button_states.buttonstate3 (the wheel word) and mirrors the result into base.buttons_pb.buttonstate3. |
| `get_orig_button_state1` | `:get_orig_button_state1() -> integer` | safe | The down word (buttonstate1) the game produced for this CreateMove, captured before any feature or script wrote the command: what the player actually pressed. CHANGED: it is read from the CreateMove-begin snapshot; it used to read the live word when the cmd object was built, after native features and earlier handlers had written it. |
| `execute_ability_indices` | `:execute_ability_indices(mask: integer) -> nil` | safe | ORs `mask` into cmd.execute_ability_indices, firing the selected ability slots this tick; also records IN_ABILITY1..IN_ABILITY4 presses on the CL_Bypass path for each slot bit set. |
| `smooth_aim` | `:smooth_aim(pos: Vector3) -> nil` | safe | Writes the camera position directly to `pos`; with an optional alpha in [0,1] linearly blends from the CreateMove-entry camera toward `pos` instead. Bypasses the PSilent reach clamp — use set_psilent_at_pos for the clamped path. |
| `set_view_roll` | `:set_view_roll(roll: number) -> nil` | safe | Overwrites base.viewangles.roll with `roll`; a no-op when the cmd or its base is missing. |
| `set_psilent_at_pos` | `:set_psilent_at_pos(pos: Vector3, reach_units: number?) -> boolean` | safe | Aim at ANY 3D world position. Optional reach_units: omit/<=0 = default clamp (~145-150u); >0 = opt-in override past ~150u (the engine hard-clamps the camera at ~150u, so it may not fully apply). false = PSilent bus busy; hold fire this tick. |
| `can_psilent_at_pos` | `:can_psilent_at_pos(pos: Vector3, reach_units: number?) -> boolean` | safe | Reachability gate for set_psilent_at_pos; pass the SAME reach_units so the gate matches the cast. |
| `set_psilent_at_entity` | `:set_psilent_at_entity(entity: PlayerPawn, reach_units: number?) -> boolean` | safe | Prioritize a SPECIFIC entity for PSilent (handle-safe, game-thread only). Optional reach_units: omit/<=0 = default clamp; >0 = opt-in override past ~150u (may not fully apply). false = stale handle / gone / bus busy. |
| `can_psilent_at_entity` | `:can_psilent_at_entity(entity: PlayerPawn, reach_units: number?) -> boolean` | safe | Reachability gate for set_psilent_at_entity; pass the SAME reach_units so the gate matches the cast. |
| `reset_camera_pos` | `:reset_camera_pos() -> nil` | safe | Restores cmd.vec_camera_position to the value captured on CreateMove entry; a no-op when nothing was captured. |
| `reset_camera_ang` | `:reset_camera_ang() -> nil` | safe | Restores cmd.ang_camera_angles to the value captured on CreateMove entry; a no-op when nothing was captured. |
| `reset_backtrack` | `:reset_backtrack() -> nil` | safe | No-op stub kept for script compatibility. |
| `disable_condition` | `:disable_condition(...: any) -> nil` | safe | No-op stub kept for script compatibility; its variadic arguments are ignored. |
| `get_orig_button_state2` | `:get_orig_button_state2() -> integer` | safe | The changed-buttons word (buttonstate2) the game produced for this CreateMove, before any feature or script wrote the command. |
| `get_orig_button_state3` | `:get_orig_button_state3() -> integer` | safe | The wheel word (buttonstate3) the game produced for this CreateMove, before any feature or script wrote the command. |
| `was_button_down` | `:was_button_down(bits: integer) -> boolean\|nil` | safe | True when any of `bits` was down on the previous command, as the last Lua handler that ran on it left it. nil off the game thread or for a cmd that is not this tick's. |
| `pulse` | `:pulse(bits: integer) -> boolean\|nil` | safe | A fresh press of `bits` now (down + changed) and a forced release on the next command, which a pulse on that command cannot override. false while the bits are being released or were already pulsed on this command, so a pulse asked for every tick lands on alternate ticks and the game sees a clean edge each time. nil off the game thread or for a cmd that is not this tick's. |
| `maintain_hold` | `:maintain_hold(bits: integer)` | safe | Keeps `bits` exactly as the previous command left them, without a new edge: down ones stay down (never re-pressed), up ones stay up (a fresh player press is swallowed). Game thread, this tick's cmd only; a no-op elsewhere. |
| `aim` | `:aim(opts: table) -> integer\|nil` | safe | Aims one request for this tick through the aim paths the user's own aim runs on and returns an aim.status number. aim.type.SILENT / MAGIC_BULLETS go through the PSilent bus (applied at the end of the tick), DEFAULT through the screen-space aimbot. Every call passes the action gate (opts.role, default "offense_auto") and Safety: the PSilent cone, the visible-aim cone and smoothing floor, the reaction floor, the headshot cap for weapon shots and the script-aim hit chance. opts: aim_type (aim.type bits), what to aim at: aim_pos (Vector3), aim_angle (Angle), custom_ang_pitch / custom_ang_yaw (the current view with that pitch / yaw), or with none of these target_ent's eye point; target_ent, ability_ent (the casting ability), smooth (1..100, replaces the aim set's DEFAULT smoothing, never below Safety's floor), allowed_min_fov (DEFAULT is READY within this many degrees, default 1), max_fov (> 0: refused beyond this angle from the view), trace_pos (the shot must reach it from where it leaves), trace_radius (> 0: a hull of that half size, traced to aim_pos when there is no trace_pos), mb_only (only a camera-shifted shot reaches: no DEFAULT drive), role, on_aimed_callback() (run on READY) and on_process_callback() (run on PENDING and AIMING). A field of the wrong type is reported as a bad argument and answers INVALID. nil for a cmd that is not the one CreateMove builds now. Game thread, from on_createmove. |
| `predict_aim_camera` | `:predict_aim_camera(target: Vector3) -> Vector3\|nil` | safe | Where the command's camera stands once the view turns to look at `target`: the third-person camera orbits the eye rigidly, so turning the view moves the point the shot leaves from. nil without a live local pawn, when no view looks at `target` (it sits inside the camera's orbit), or for a cmd that is not this tick's. |
| `predict_magic_bullets_origin` | `:predict_magic_bullets_origin(target: Vector3, ability?: Ability) -> Vector3\|nil` | safe | Where a magic-bullets (PSilent) shot at `target` leaves from: the camera slid across its unchanged view until the view line meets `target`, lifted by the projectile's drop. `ability` is a projectile ability, omitted for the weapon's bullet. nil off the game thread, without a live local pawn or projectile speed, for a target behind the view or past the camera reach the PSilent commit accepts. |
| `get_view_angles` | `:get_view_angles() -> Angle` | safe | Returns the user command's view angles, or a zero QAngle when `self` is nil. |
| `set_view_angles` | `:set_view_angles(v: any)` | safe | Writes the view angles on the user command from v. |

### CUserCmd

`usertype` · tier `safe` — Raw SDK command handle (lighter surface than UserCmd).

_No members._

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
| `Gear` | `:Gear(name: string, icon?: string, small?: boolean) -> MenuNode` | safe | Gets or creates a child Gear container with the given name; the optional icon sets its icon string and the optional mirror flag is accepted as a trailing argument. Returns the gear MenuNode. |
| `Create` | `:Create(name: string, side?: integer) -> MenuNode` | safe | Legacy alias for Group; optional side is an Enum.GroupSide (Left/Right) column pin. |
| `Find` | `:Find(name: string) -> MenuNode\|nil` | safe | Returns the direct child MenuNode with the given name, or an empty MenuNode if there is no such child. |
| `Switch` | `:Switch(name: string, default?: boolean, icon?: string, tooltip?: string) -> MenuNode` | safe | Trailing string args are absorbed as (icon, tooltip) in that order; the first string is the icon, not the tooltip. |
| `Slider` | `:Slider(name: string, min: number, max: number, default?: number, format?: string) -> MenuNode` | safe | Float slider. Order is (min, max, default). default defaults to min. Last arg is a printf-style FORMAT like "%.1f", NOT a tooltip (use :Tooltip()). |
| `SliderInt` | `:SliderInt(name: string, min: integer, max: integer, default?: integer, format?: string) -> MenuNode` | safe | Integer slider. Order is (min, max, default). default defaults to min. Last arg is a printf-style FORMAT like "%d", NOT a tooltip (use :Tooltip()). |
| `SliderFloat` | `:SliderFloat(name: string, min: number, max: number, default?: number, format?: string) -> MenuNode` | safe | Alias of Slider. Order is (min, max, default). default defaults to min. Last arg is a printf-style FORMAT like "%.1f", NOT a tooltip (use :Tooltip()). |
| `Combo` | `:Combo(name: string, items: string[], default?: integer, icon?: string, tooltip?: string) -> MenuNode` | safe | Trailing string args after default are absorbed as (icon, tooltip); the first string is the icon, not the tooltip. Numeric items are converted to text and cut at 47 characters. |
| `MultiCombo` | `:MultiCombo(name: string, items: string[], default_on?: string[], icon?: string, tooltip?: string) -> MenuNode` | safe | default_on is a list of item names to start enabled (all OFF if omitted). Trailing string args are absorbed as (icon, tooltip). |
| `MultiSelect` | `:MultiSelect(name: string, items: string[], default_on?: string[], icon?: string, tooltip?: string) -> MenuNode` | safe | default_on is a list of item names to start enabled (all OFF if omitted). Trailing string args are absorbed as (icon, tooltip). |
| `Bind` | `:Bind(name: string, default_key?: integer, icon?: string, tooltip?: string) -> MenuNode` | safe | default_key is an Enum.ButtonCode. Trailing string args are absorbed as (icon, tooltip); the first string is the icon, not the tooltip. |
| `ColorPicker` | `:ColorPicker(name: string, r?: number, g?: number, b?: number, a?: number) -> MenuNode` | safe | Numeric-channel (0-255) form shown; also accepts ColorPicker(name, Color) plus trailing icon?/tooltip? strings. |
| `Button` | `:Button(name: string, callback: function) -> MenuNode` | safe | Adds a Button leaf with the given label and stores the supplied function as its click callback. Returns the button MenuNode. |
| `Label` | `:Label(text: string) -> MenuNode` | safe | Adds a static Label leaf that renders the given text as a row. Returns the label MenuNode. |
| `Input` | `:Input(name: string, default?: string) -> MenuNode` | safe | Text input. Takes only (name, default) - it has NO tooltip parameter; apply a tooltip via the separate :Tooltip() decorator. |
| `Tooltip` | `:Tooltip(text: string) -> MenuNode` | safe | Sets the node's tooltip string and marks the menu tree changed. Returns self. |
| `Icon` | `:Icon(icon: string) -> MenuNode` | safe | Sets the node's icon string and marks the menu tree changed. Returns self. |
| `Image` | `:Image(image: string) -> MenuNode` | safe | Sets the node's image string and marks the menu tree changed. Returns self. |
| `SetCallback` | `:SetCallback(fn: function) -> MenuNode` | safe | Replaces the node's change callback with the given function; it fires when the leaf's value changes. Returns self. |
| `Visible` | `:Visible(v: boolean) -> MenuNode` | safe | Sets whether the node is visible and marks the menu tree changed. Returns self. |
| `Remove` | `:Remove() -> boolean` | safe | Permanently unlink this node (and its descendants) from the menu tree — for probe/temporary nodes that only Visible(false) could hide before. ConfigStore values keyed by its path are kept. The row's descriptors are unregistered on Remove, so a slug lookup of the removed row stops resolving until it is recreated; recreating it returns the same id and value. |
| `Disabled` | `:Disabled(v: boolean) -> MenuNode` | safe | Sets the node's disabled flag; called with no argument it defaults to true (disabled). Returns self. |
| `VisibleCondition` | `:VisibleCondition(fn: fun():boolean) -> MenuNode` | safe | Installs a predicate evaluated each frame to decide the node's visibility; the function returns a boolean. Returns self. |
| `DisableCondition` | `:DisableCondition(fn: fun():boolean) -> MenuNode` | safe | Installs a predicate evaluated each frame to decide the node's disabled state; returning true disables the node. Returns self. |
| `link_to_ui_visible_condition` | `:link_to_ui_visible_condition(other: MenuNode) -> MenuNode` | safe | Links the node's visibility to another MenuNode so that this node inherits that node's visible-condition result. Returns self. |
| `link_to_ui_disable_condition` | `:link_to_ui_disable_condition(other: MenuNode) -> MenuNode` | safe | Links the node's disabled state to another MenuNode so that this node inherits that node's disable-condition result. Returns self. |
| `Get` | `:Get() -> any` | safe | Reads the leaf's current value typed to its kind: bool for Switch, int for SliderInt/Combo/Hitbox/Bind, float for SliderFloat, string for Input, a color object for ColorPicker, or an {item = on} table for MultiCombo/MultiSelect. |
| `Set` | `:Set(value: any) -> MenuNode` | safe | Writes a new value into the leaf, matched to its kind: bool for Switch, int for SliderInt/Combo/Bind, number for SliderFloat, string for Input, or an {item = on} table for MultiCombo/MultiSelect; values are clamped by the config system. |
| `SetColor` | `:SetColor(r: number, g: number, b: number, a: number) -> MenuNode` | safe | Writes the leaf's color from 0–255 r, g, b components with an optional alpha (defaults to 255). |
| `GetBool` | `:GetBool() -> boolean` | safe | Returns the leaf's current value as a boolean; any non-zero numeric value reads as true. |
| `GetInt` | `:GetInt() -> integer` | safe | Returns the leaf's current value coerced to an int. |
| `GetFloat` | `:GetFloat() -> number` | safe | Returns the leaf's current value coerced to a float. |
| `GetString` | `:GetString() -> string` | safe | Returns the leaf's current string value, or an empty string when the leaf has no registered desc. |
| `IsDown` | `:IsDown() -> boolean` | safe | Returns true while the leaf's bound hotkey is currently held; always false for Switch leaves. |
| `IsPressed` | `:IsPressed() -> boolean` | safe | Returns true on the frame the leaf's bound hotkey transitions from up to down; suppressed while the user is typing in-game. |
| `IsToggled` | `:IsToggled() -> boolean` | safe | Returns the latched toggle state of the leaf's hotkey; the latch flips on each key press (edge triggered) and is held across frames. Suppressed while the user is typing. |
| `SetToggled` | `:SetToggled(v: boolean) -> MenuNode` | safe | Overwrites the latched toggle state of the leaf's hotkey to the given value. |
| `Name` | `:Name() -> string` | safe | Returns the node's name string. |
| `Path` | `:Path() -> string` | safe | Returns the node's full slash-delimited menu path. |
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
| `combo` | `:combo(name: string, items: table, def: integer?, ...: any) -> MenuNode` | safe | Adds (or returns) a combo-box leaf whose entries come from `items`; the optional default is the 0-based index (defaults to 0). Returns the leaf node for chaining. |
| `icon` | `:icon(icon: string) -> MenuNode` | safe | Sets the leading icon identifier shown next to this node and marks the menu tree dirty; returns self for chaining. |
| `switch` | `:switch(name: string, def: boolean?, ...: any) -> MenuNode` | safe | Adds (or returns) a boolean switch leaf under this node with an optional default (false when omitted). Trailing variadics are consumed as node-decorators. |
| `create` | `:create(name: string, side: integer\|nil) -> MenuNode` | safe | Alias of `MenuNode.Group`. Gets or creates a `Group` container under this node (optionally pinning its side) and returns a MenuNode for it. |
| `image` | `:image(path: string) -> MenuNode` | safe | Alias of `MenuNode.SetImage`. Sets the node's image path and returns self for chaining. |
| `theme_picker` | `:theme_picker(name: string) -> MenuNode` | safe | Alias of `MenuNode.ThemePicker`. Gets or creates a Combo leaf seeded with the built-in theme list (`UmbrellaDefault`, `WhiteDefault2`) and returns a MenuNode for it. |
| `custom_bind` | `:custom_bind(...: any) -> MenuNode` | safe | Alias of `MenuNode:CustomBind`: adds a custom bind row under this node. |
| `input` | `:input(...: any) -> MenuNode` | safe | Alias of `MenuNode:Input`: adds a text input row under this node. |
| `toggle` | `:toggle() -> boolean` | safe | Alias of `MenuNode:IsToggled`: returns the node's current toggled state. |
| `disable` | `:disable(disabled: boolean?) -> MenuNode` | safe | Alias of `MenuNode.Disabled`: sets the node's disabled flag (default true) and returns self. |
| `label` | `:label(text: string) -> MenuNode` | safe | Appends a Label leaf under this node and returns a handle to it. |
| `tooltip` | `:tooltip(text: string) -> MenuNode` | safe | Sets the node's hover tooltip text and returns self. |
| `disable_condition` | `:disable_condition(fn: function) -> MenuNode` | safe | Installs fn as the node's disable-condition predicate; returns self for chaining. |
| `multicombo` | `:multicombo(name: string, items: table, defaults: table?, ...: any) -> MenuNode` | safe | Adds (or reuses) a MultiCombo leaf under self, seeding its options from items and initial on-set from defaults; trailing varargs are absorbed as leaf settings. |
| `unset_callback` | `:unset_callback(...: any) -> MenuNode` | safe | Clears any change callback previously set on the node; returns self for chaining. |
| `down` | `:down() -> boolean` | safe | Alias of MenuNode.IsDown. |
| `multiselect` | `:multiselect(...: any) -> MenuNode` | safe | Alias of MenuNode.MultiSelect. |
| `visible` | `:visible(visible: boolean) -> MenuNode` | safe | Alias of MenuNode.Visible (invokes SetVisible). |
| `down_once` | `:down_once() -> boolean` | safe | Alias of `MenuNode.IsPressed`: true on the frame the node's bound key goes from up to down, suppressed while a text input is capturing keys. |
| `remove` | `:remove() -> boolean` | safe | Detaches this node (and its subtree) from the menu tree; returns true on success. |
| `visible_condition` | `:visible_condition(fn: fun(...):any) -> MenuNode` | safe | Sets `fn` as the per-frame predicate controlling whether this node is drawn; returns self for chaining. |
| `enable` | `:enable(enabled: boolean\|nil) -> MenuNode` | safe | Alias of `MenuNode:SetEnabled` — clears the node's disabled flag when `enabled` is true (or omitted), sets it otherwise, and returns the node for chaining. |
| `section` | `:section(name: string, side: integer\|nil) -> MenuNode` | safe | Gets or creates a Section container named `name` under the node, optionally pinning it to a side, and returns the section node. |
| `Enabled` | `:Enabled(enabled: boolean) -> MenuNode` | safe | Alias of MenuNode:enable / :set_enabled; sets the node's disabled flag to !enabled and returns self. |
| `esp_preview` | `:esp_preview(...: any) -> MenuNode` | safe | Adds an ESP preview widget child to this node (bound to LuaNode::EspPreview). |
| `separator` | `:separator() -> MenuNode` | safe | Appends a visual separator row to this node. |
| `Separator` | `:Separator() -> MenuNode` | safe | Appends a Separator leaf under this node (with a child-index-derived synthetic name) and returns the leaf wrapper. |
| `find` | `:find(name: string) -> MenuNode` | safe | Alias of `MenuNode.Find`; returns the child node with the given name, or an empty handle when not found. |
| `set` | `:set(value: any) -> nil` | safe | Writes `value` into this control's config entry; the accepted Lua type is picked from the node kind (bool for Switch, int for SliderInt, float for Slider, string for text controls, etc.). |
| `ToolTip` | `:ToolTip(text: string) -> MenuNode` | safe | Alias of `MenuNode.Tooltip`: sets the node's tooltip text and returns self for chaining. |
| `gear` | `:gear(name: string, icon: string?, mirror: boolean?) -> MenuNode` | safe | Alias of `MenuNode.Gear`: creates (or reuses) a gear container child under this node; optionally sets its icon and mirror flag. |
| `set_callback` | `:set_callback(fn: function) -> MenuNode` | safe | Alias of `MenuNode.SetCallback`: installs the node's change callback and returns self. |
| `add` | `:add(item: string, ...: any) -> MenuNode` | safe | Appends `item` to this node's items list (marking the node as an icon-grid node), seeds a persistent bool for the item, and returns `self` for chaining. |
| `gear_mirror` | `:gear_mirror(mirror: boolean) -> MenuNode` | safe | Sets the node's gear-mirror flag and returns `self`. |
| `set_enabled` | `:set_enabled(enabled: boolean\|nil) -> MenuNode` | safe | Sets `disabled` to the inverse of `enabled` (defaults to enabled when omitted) and returns `self`. |
| `bind` | `:bind(...: any) -> any` | safe | Binds the node to a storage path or default value (dispatches to `LuaNode::Bind`). |
| `get` | `:get() -> any` | safe | Reads the node's current value in its native type (dispatches to `LuaNode::Get`). |
| `set_toggle` | `:set_toggle(on: boolean)` | safe | Sets the node's toggled state (dispatches to `LuaNode::SetToggled`). |
| `button` | `:button(name: string, cb: function) -> MenuNode` | safe | Adds (or finds) a Button leaf under self and binds cb as its click callback; returns the leaf node. |
| `group` | `:group(name: string, side?: integer) -> MenuNode` | safe | Adds (or finds) a Group container under self; optional side pins the column (0=Left, 1=Right, other=Auto). Returns the group node. |
| `slider` | `:slider(name: string, min: number, max: number, default?: number, format?: string, ...: any) -> MenuNode` | safe | Adds (or finds) a float slider leaf (bounds, default, printf-style format "%.1f" by default); extra args are absorbed as trailing tooltip/icon/etc. Returns the leaf node. |
| `colorattach` | `:colorattach(name: string, ...: any) -> MenuNode` | safe | Alias of `MenuNode.ColorAttach`: creates (or reuses) a ColorAttach leaf on this node named `name`, reads a default color from the trailing args, and returns the leaf as a MenuNode. |
| `held` | `:held() -> boolean` | safe | Alias of `MenuNode.key_held`: returns true when the node's bound key (via its ImGuiKey -> VK mapping) is currently held in-game, excluding Switch nodes and periods where typing is active. |
| `slider_float` | `:slider_float(name: string, min: number, max: number, default: number\|nil, format: string\|nil, ...: any) -> MenuNode` | safe | Alias of `MenuNode.Slider`: creates (or reuses) a float slider leaf named `name` with range [min, max], default value (defaults to min), printf-style format (default "%.1f"), and returns the leaf as a MenuNode. |
| `colorpicker` | `:colorpicker(name: string, ...: any) -> MenuNode` | safe | Alias of `MenuNode.ColorPicker` — adds a color-picker leaf; a Color in the trailing args seeds the default. |
| `hitbox` | `:hitbox(name: string, defaults: table\|nil) -> MenuNode` | safe | Alias of `MenuNode.Hitbox` — adds a hitbox-region picker leaf using the title's hitbox groups; the optional defaults table seeds the per-region state bitmask. |
| `slider_int` | `:slider_int(name: string, min: integer, max: integer, def: integer\|nil, fmt: string\|nil, ...: any) -> MenuNode` | safe | Alias of `MenuNode.SliderInt` — adds an integer-slider leaf; defaults to `min` when `def` is omitted and `%d` for the format. |

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
| `write` | `:write(data: string) -> boolean` | privileged | Writes the given string to the open handle via WriteFile (seeking to end first when the file was opened in append mode); returns true only when every byte was written. |
| `close` | `:close()` | privileged | Closes the underlying Windows handle and marks the file not-open; returns true if the call actually closed an open handle, false if it was already closed. |
| `is_open` | `:is_open() -> boolean` | privileged | Whether the file is still open (false after close). |
| `lines` | `:lines() -> string[]` | privileged | 1-indexed array of the remaining lines from the current cursor. |
| `seek` | `:seek(whence?: string, offset?: integer) -> integer` | privileged | Move the cursor. whence = "set"\|"cur"\|"end" (default "cur"); returns the new absolute position (-1 on failure). |
| `flush` | `:flush() -> boolean` | privileged | Flush buffered writes to disk. |

### GameEvent

`usertype` · tier `safe` — Game event (on_game_event / user-message payload).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_int` | `:get_int(key: string) -> integer` | safe | Returns the integer field named by key from the live IGameEvent, or 0 if the event is no longer live or the field is absent. |
| `get_float` | `:get_float(key: string) -> number` | safe | Returns the float field named by key from the live IGameEvent, or 0 if the event is no longer live or the field is absent. |
| `get_string` | `:get_string(key: string) -> string` | safe | Returns the string field named by key from the live IGameEvent (capped at 512 chars); empty when the event is no longer live. |
| `get_bool` | `:get_bool(key: string) -> boolean` | safe | Returns the boolean field named by key from the live IGameEvent, or false if the event is no longer live or the field is absent. |
| `get_name` | `:get_name() -> string` | safe | Returns the event name captured when this GameEvent was dispatched. |
| `get_entindex` | `:get_entindex(key: string) -> integer` | safe | Stub returning 0 — entity-index fields are not exposed through this reader. |
| `get_float_default` | `:get_float_default(key: string, default: number) -> number` | safe | Returns the event's float field named `key`, or `default` when the field is absent. |
| `get_int_default` | `:get_int_default(key: string, def: integer) -> integer` | safe | Reads integer field `key` from the live game event, returning `def` when the event is dead or the key is absent. |
| `get_playerslot` | `:get_playerslot(key: string) -> integer` | safe | Stub that always returns 0. |
| `get_string_default` | `:get_string_default(key: string, def: string) -> string` | safe | Returns the event's string value for key capped at 512 bytes, or def when the event is not live or the key is absent. |
| `get_userid` | `:get_userid(key: string) -> integer` | safe | Stub that always returns 0; user-id fields are not surfaced from LuaGameEvent. |
| `is_valid` | `:is_valid() -> boolean` | safe | Returns true when the captured game event is still live. |
| `name` | `:name() -> string` | safe | Captured event name as recorded when the GameEvent wrapper was created. |
| `to_table` | `:to_table() -> table` | safe | Returns an empty table; full field enumeration is not exposed. |
| `valid` | `:valid() -> boolean` | safe | True when the wrapper still points at a live `IGameEvent`. |
| `get_address` | `:get_address() -> integer\|nil` | safe | Returns the native IGameEvent pointer as an unsigned 64-bit integer, gated by the raw-read capability; returns nothing when the capability is denied. |
| `get_bool_default` | `:get_bool_default(key: string, def: boolean) -> boolean` | safe | Reads a boolean field from the live game event; returns `def` when the event is dead or the field is absent. |

### raw_struct

`usertype` · tier `privileged` — Typed read/write view over a native struct pointer.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_int` | `:get_int(field: string) -> integer` | privileged | Reads a 32-bit signed int at the field's resolved schema offset; returns 0 when the field is unknown on the class chain or the address is not readable. |
| `get_float` | `:get_float(field: string) -> number` | privileged | Reads a 32-bit float at the field's resolved schema offset; returns 0 when the field is unknown or the address is not readable. |
| `get_bool` | `:get_bool(field: string) -> boolean` | privileged | Reads a one-byte bool at the field's resolved schema offset; returns false when the field is unknown or the address is not readable. |
| `get_vec` | `:get_vec(field: string) -> Vector3` | privileged | Reads three consecutive floats at the field's offset and returns them as a Vector3; returns a zero vector when the field is unknown or the memory is not readable. |
| `set_int` | `:set_int(field: string, value: integer) -> nil` | privileged | Writes a 32-bit signed int at the field's resolved schema offset; returns true on success, false when the field is unknown or the address is not writable. |
| `set_float` | `:set_float(field: string, value: number) -> nil` | privileged | Writes a 32-bit float at the field's resolved schema offset; returns true on success, false when the field is unknown or the address is not writable. |
| `set_bool` | `:set_bool(field: string, value: boolean) -> nil` | privileged | Writes a one-byte bool at the field's resolved schema offset; returns true on success, false when the field is unknown or the address is not writable. |
| `set_vec` | `:set_vec(field: string, value: Vector3) -> nil` | privileged | Writes a Vector3 as three consecutive floats at the field's offset; returns true on success, false when the field is unknown or the memory is not writable. |
| `offset_of` | `:offset_of(field: string) -> integer` | privileged | Returns the byte offset of a named field, walking the schema class chain of this struct; returns 0 when the field is not found. |
| `class_name` | `:class_name() -> string` | privileged | Returns the primary (most-derived) schema class name this raw_struct was constructed for. |
| `address` | `:address() -> integer` | privileged | Returns the raw base address of the struct as an unsigned integer (0 when the struct is empty). |
| `get_class_name` | `:get_class_name() -> string` | safe | Primary (most-derived) schema class name attached to this struct view. |
| `set_qangle` | `:set_qangle(field: string, value: Angle) -> boolean` | safe | Writes a QAngle (pitch, yaw, roll) at the named field; returns false when the field is unknown or the destination is not writable. |
| `get_color` | `:get_color(field: string) -> Color` | safe | Reads a 32-bit ARGB value at the field's offset and returns it as a Color; zero Color when the field has no offset or the memory is not readable. |
| `set_uint` | `:set_uint(field: string, value: integer) -> boolean` | safe | Writes a 32-bit unsigned integer at the field's offset; returns false when the field has no offset or the target bytes are not writable. |
| `get_handle` | `:get_handle(field: string) -> CHandle` | safe | Reads field `field` as a 32-bit CHandle; returns a default CHandle when the field is unknown or the memory is unreadable. |
| `sub_struct` | `:sub_struct(field: string, childClass: string) -> raw_struct` | safe | Dereferences pointer field `field` and returns a `raw_struct` for the pointed-to object typed as `childClass`; returns an empty raw_struct when the field is unknown or unreadable. |
| `get_int64` | `:get_int64(field: string) -> integer` | safe | Reads a 64-bit int at the schema offset for `field`; returns 0 when the field is unknown or the address isn't readable. |
| `valid` | `:valid() -> boolean` | safe | True when the wrapped base address is non-zero. |
| `get_ptr` | `:get_ptr(field: string) -> integer` | safe | Reads a pointer-sized value at the resolved field offset; returns 0 when the field is unknown or the address is unreadable. |
| `get_qangle` | `:get_qangle(field: string) -> Angle` | safe | Reads three floats at the field's schema offset and returns them as a QAngle; zero QAngle when the field is unknown or the memory is not readable. |
| `get_short` | `:get_short(field: string) -> integer` | safe | Reads a signed 16-bit value from the struct at the resolved offset of `field`; returns 0 when the field is unknown or memory is unreadable. |
| `get_string` | `:get_string(field: string) -> string` | safe | Reads a pointer-to-cstring at the field's offset and returns the referenced string; empty string if the field is unknown, the pointer is null, or either address is unreadable. |
| `get_uint` | `:get_uint(field: string) -> integer` | safe | Reads a 32-bit unsigned int at the field's offset; returns 0 when the field is unknown or the address is not readable. |
| `get_vec2` | `:get_vec2(field: string) -> Vector3` | safe | Reads two consecutive floats at the schema offset of `field` into a `Vector3` with `z = 0`; returns a zero vector when the offset is missing or the memory is unreadable. |
| `has_field` | `:has_field(field: string) -> boolean` | safe | True when the field resolves to a non-zero offset in this struct's class chain. |
| `is_valid` | `:is_valid() -> boolean` | safe | Returns true if the raw struct holds a non-zero base pointer. |
| `rebase` | `:rebase(offset: integer) -> raw_struct` | safe | Returns a new raw_struct whose base is self.base + offset while keeping the inherited class chain; returns an empty struct when self has no base. |
| `class_chain` | `:class_chain() -> table` | safe | Returns an array table of class names in this struct's schema inheritance chain. |
| `set_handle` | `:set_handle(field: string, handle: any) -> boolean` | safe | Writes the raw 32-bit CHandle value into the given field; returns false when the field is unknown or the target address is not writable. |
| `get_address` | `:get_address() -> integer` | safe | Returns the base address of the wrapped struct. |
| `set_int64` | `:set_int64(field: string, value: integer) -> boolean` | safe | Writes a 64-bit integer to `field` on the wrapped struct; returns false when the field is unknown or the target address is not writable, true otherwise. |
| `get_byte` | `:get_byte(field: string) -> integer` | safe | Reads an unsigned byte at the field's offset and returns it as an int; 0 when the offset is unknown or the address is unreadable. |
| `set_ptr` | `:set_ptr(field: string, v: integer) -> boolean` | safe | Writes a pointer-sized integer at the field's offset; false when the offset is unknown or the address is not writable. |

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
| `read_int` | `mem.read_int(address: integer) -> integer\|nil` | privileged | Reads a 32-bit signed int at the given address through the gated reader (alias of read_int32); returns nil plus a reason string when the address fails the read gate. |
| `read_int64` | `mem.read_int64(address: integer) -> integer\|nil` | privileged | Reads a 64-bit signed int at the given address through the gated reader; returns nil plus a reason string on failure. |
| `read_float` | `mem.read_float(address: integer) -> number\|nil` | privileged | Reads a 32-bit float at the given address through the gated reader; returns nil plus a reason string on failure. |
| `read_double` | `mem.read_double(address: integer) -> number\|nil` | privileged | Reads a 64-bit double at the given address through the gated reader; returns nil plus a reason string on failure. |
| `read_bool` | `mem.read_bool(address: integer) -> boolean\|nil` | privileged | Reads one byte at the given address and pushes it as a Lua boolean (non-zero → true); returns nil plus a reason string on failure. |
| `read_byte` | `mem.read_byte(address: integer) -> integer\|nil` | privileged | Reads a single unsigned byte at the given address and returns it as an integer; returns nil plus a reason string on failure. |
| `read_ptr` | `mem.read_ptr(address: integer) -> integer\|nil` | privileged | Reads a pointer-sized value at the given address and returns it as light userdata; returns nil plus a reason string on failure. |
| `read_vec3` | `mem.read_vec3(address: integer) -> Vector3\|nil` | privileged | Reads three consecutive floats at the given address and returns them as a table { x, y, z }; returns nil plus a reason string on failure. |
| `read_string` | `mem.read_string(address: integer, max_len?: integer) -> string\|nil` | privileged | Reads a NUL-terminated ASCII string at the given address, up to an optional byte cap (default 4096, clamped to the 1 MB read limit); walks the memory in 256-byte guarded chunks and stops at the first NUL or on fault. |
| `write_int` | `mem.write_int(address: integer, value: integer) -> boolean` | privileged | Writes a 32-bit signed int at the given address through the gated writer (alias of write_int32); requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_int64` | `mem.write_int64(address: integer, value: integer) -> boolean` | privileged | Writes a 64-bit signed int at the given address through the gated writer; requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_float` | `mem.write_float(address: integer, value: number) -> boolean` | privileged | Writes a 32-bit float at the given address through the gated writer; requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_double` | `mem.write_double(address: integer, value: number) -> boolean` | privileged | Writes a 64-bit double at the given address through the gated writer; requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_bool` | `mem.write_bool(address: integer, value: boolean) -> boolean` | privileged | Writes a single byte (1 or 0) representing a boolean at the given address; requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_byte` | `mem.write_byte(address: integer, value: integer) -> boolean` | privileged | Writes a single unsigned byte at the given address; requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_ptr` | `mem.write_ptr(address: integer, value: integer) -> boolean` | privileged | Writes a pointer-sized value at the given address (the value may be a lightuserdata or integer); requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_vec3` | `mem.write_vec3(address: integer, value: Vector3) -> boolean` | privileged | Writes three consecutive floats at the given address; accepts either a { x, y, z } table or three loose number arguments. Requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `write_string` | `mem.write_string(address: integer, value: string) -> boolean` | privileged | Writes the given Lua string, including its trailing NUL, at the address; requires the mem.write capability and returns true on success, false plus a reason string otherwise. |
| `module_base` | `mem.module_base(module_name: string) -> integer\|nil` | privileged | Looks up a loaded module by name (via FNV1a hash over the PEB module list) and returns its image base as light userdata, or nil when the module is not loaded. |
| `pattern_scan` | `mem.pattern_scan(module_name: string, pattern: string, offset?: integer) -> integer\|nil` | privileged | Scans the named module for an IDA-style byte pattern and returns the first match address as light userdata, or nil if nothing matches. The module name must be in the title's native-module allowlist, the scan range is gate-checked, and the scan runs under an SEH guard so a region unmapped mid-scan returns nil plus a reason string. |
| `get_call_target` | `mem.get_call_target(address: integer) -> integer\|nil` | privileged | Disabled by policy: returns nil plus the message "memory.get_call_target: use read_bytes + a Lua-side disassembler." (gated behind the mem capability). |
| `get_ptr_address` | `mem.get_ptr_address(address: integer, disp_offset?: integer, instr_len?: integer) -> integer\|nil` | privileged | Disabled by policy: returns nil plus the message "memory.get_ptr_address: pointer relocation math from Lua is disabled." (gated behind the mem capability). |
| `vfunc` | `mem.vfunc(instance: integer, index: integer) -> integer\|nil` | privileged | Reads the vtable pointer at the given instance address, then returns the function pointer stored at the requested slot index as an integer. The slot index is capped at 4096, each read is gated, and the resolved target is validated with CheckCallTarget; returns nil plus a reason string on any gate failure. |
| `call` | `mem.call(address: integer, ret_type: string, arg_types: string[], ...: any) -> any` | privileged | Disabled by policy: returns nil plus the message "memory.call: use ffi.func for controlled call against the game-DLL allowlist." (gated behind the mem capability). |
| `alloc` | `mem.alloc(...: any) -> nil,string` | safe | Refusal stub: returns `nil, reason` — page allocation from Lua is disabled by policy. |
| `read_int16` | `mem.read_int16(addr: integer) -> integer\|nil` | safe | Reads a signed 16-bit value at `addr` through the gated reader; nil if the read capability is denied or the fetch fails. |
| `string_scan` | `mem.string_scan(...: any) -> nil,string` | safe | Refusal stub: returns `nil, reason` — scan a copy from `mem.read_bytes` on the Lua side instead. |
| `aob_scan` | `mem.aob_scan(module: string, pattern: string) -> integer\|nil` | safe | Scans the named allowlisted module for an IDA-style AoB pattern and returns the hit address; returns nil with a reason string on cap denial, bad arguments, disallowed module, or unloaded module. |
| `read_int32` | `mem.read_int32(address: integer) -> integer\|nil` | safe | Reads a 32-bit signed integer from `address` through the gated reader; returns nil with a reason string if the read is refused or unmapped. |
| `version` | `mem.version() -> string` | safe | Returns the memory-surface version tag string (`avalanche.memory.v4`). |
| `call_convention` | `mem.call_convention(...: any) -> any` | safe | Refusal stub: calling-convention selection from Lua is disabled by policy. |
| `read_int8` | `mem.read_int8(addr: integer) -> integer\|nil` | safe | Reads a signed 8-bit integer at `addr`; returns nil (and a reason string) when the read capability is denied or the address is unreadable. |
| `virtual_query` | `mem.virtual_query(...: any) -> any` | safe | Refusal stub: VAD introspection from Lua is disabled by policy. |
| `enumerate_modules` | `mem.enumerate_modules() -> table` | safe | Returns an array of loaded-module descriptors by walking the module list. |
| `read_matrix` | `mem.read_matrix(address: integer) -> table\|nil` | safe | Reads 12 contiguous floats from `address` into a 1-indexed array; returns nil without the read capability or on a gated-read failure. |
| `write_bytes` | `mem.write_bytes(address: integer, data: string) -> boolean` | safe | Writes the raw bytes of `data` to `address`; returns true on success, false (or a gated-write failure pair) otherwise. |
| `find_pattern` | `mem.find_pattern(module: string, pattern: string) -> any\|nil` | safe | Alias of `mem.pattern_scan`. |
| `read_qangle` | `mem.read_qangle(addr: integer) -> table\|nil` | safe | Reads three floats at addr through the read-gate and returns {pitch, yaw, roll}; nil (plus reason) if the capability or read is refused. |
| `write_int16` | `mem.write_int16(addr: integer, value: integer) -> boolean` | safe | Writes a 16-bit signed integer at addr through the write-gate; refused if the write capability is denied. |
| `free` | `mem.free(...: any) -> boolean, string` | safe | Refusal binding: returns false and the reason "memory.free: page free from Lua is disabled by policy." |
| `read_uint16` | `mem.read_uint16(address: integer) -> integer\|nil` | safe | Reads a uint16 at address through the gated-read surface and returns it as an integer; on gate failure returns nil plus a reason string, and nil with no reason when the mem capability is denied. |
| `write_int32` | `mem.write_int32(address: integer, value: integer) -> boolean` | safe | Writes a signed 32-bit value at address through the gated-write surface and returns true on success; on gate failure returns false plus a reason string, and false with no reason when the mem.write capability is denied. |
| `game_module_base` | `mem.game_module_base() -> any\|nil` | safe | Returns the target game module's base address as a light userdata, or nil if not yet located. |
| `read_uint32` | `mem.read_uint32(addr: integer\|any) -> integer\|nil` | safe | Reads a 32-bit unsigned integer at `addr` through the memory gate; returns nil, reason on a gated-read failure or when the `mem` capability is denied. |
| `write_int8` | `mem.write_int8(addr: integer\|any, value: integer) -> boolean` | safe | Writes a signed 8-bit value at `addr` through the memory gate; returns false if the `mem.write` capability is denied or the gated write fails (with a reason as the second return). |
| `get_module_base` | `mem.get_module_base(name: string) -> userdata\|nil` | safe | Light-userdata base address of the loaded module `name` (FNV-1a hashed, resolved via the PEB), or nil if `name` is empty or the module is not mapped. |
| `read_uint64` | `mem.read_uint64(address: integer) -> integer\|nil` | safe | Reads an unsigned 64-bit integer at `address` after a gated-read check; returns nil on an unreadable region. |
| `write_qangle` | `mem.write_qangle(address: integer, pitch_or_table: number\|table, yaw: number\|nil, roll: number\|nil) -> boolean` | safe | Writes a 12-byte `QAngle` (pitch/yaw/roll floats) at `address`; the second argument may be a `{pitch, yaw, roll}` table or three scalars. Returns false if the write capability is denied or the region is not writable. |
| `has_read_surface` | `mem.has_read_surface() -> boolean` | safe | Always returns true; signals that the gated memory-read surface is present. |
| `read_uint8` | `mem.read_uint8(address: integer) -> integer\|nil` | safe | Reads a uint8 at the given address through the gated read surface; returns nil if the mem capability is denied or the gated read fails. |
| `write_uint16` | `mem.write_uint16(address: integer, value: integer) -> boolean` | safe | Writes a uint16 at the given address through the gated write surface; returns false if the mem.write capability is denied or the gated write fails. |
| `has_write_surface` | `mem.has_write_surface() -> boolean` | safe | Always returns true; a probe used by scripts to confirm the memory-write surface is wired up. |
| `read_utf16` | `mem.read_utf16(address: integer, wchar_count: integer?) -> string\|nil` | safe | Reads a UTF-16 string of up to `wchar_count` wide characters (default 2048, clamped so the byte count stays within the memory read cap); returns nil when the read capability is denied or the gated read fails. |
| `write_uint32` | `mem.write_uint32(address: integer, value: integer) -> boolean` | safe | Writes a 32-bit unsigned integer; returns false if the write capability is denied or the gated write faults. |
| `hex_dump` | `mem.hex_dump(...: any) -> nil, string` | safe | Refusal stub: returns a policy message instead of dumping memory. Build a hex view on top of `mem.read_bytes` at the Lua layer. |
| `read_utf8` | `mem.read_utf8(addr: integer, max_bytes: integer?) -> string\|nil` | safe | Alias of `mem.read_string`; reads a null-terminated byte string at the address, with the usual read-capability and bounds checks. |
| `write_uint64` | `mem.write_uint64(addr: integer, value: integer) -> boolean` | safe | Writes an unsigned 64-bit integer at the address through the gated write surface; returns success. Requires the write capability. |
| `ida_scan` | `mem.ida_scan(module: string, pattern: string) -> integer\|nil, string\|nil` | safe | Alias of `memory.pattern_scan`. |
| `read_vector3` | `mem.read_vector3(addr: integer) -> table\|nil, string\|nil` | safe | Reads three contiguous floats at `addr` and returns them as `{x=, y=, z=}`; returns nil (plus a reason) if the read capability is denied or the gated read fails. |
| `write_uint8` | `mem.write_uint8(addr: integer, value: integer) -> boolean` | safe | Writes a `uint8_t` at `addr`; requires memory-write capability and returns false (plus a reason) if the gated write is refused. |
| `is_module_loaded` | `mem.is_module_loaded(name: string) -> boolean` | safe | Returns true when a module whose name hashes to the given string is currently loaded in the process; false for an empty name. |
| `relative_scan` | `mem.relative_scan(...: any) -> nil,string` | safe | Refusal stub: returns nil plus a reason telling the caller to use `read_bytes` plus a Lua-side disassembler. |
| `write_vector3` | `mem.write_vector3(addr: integer, v: Vector3\|table\|number, y: number?, z: number?) -> boolean` | safe | Writes three contiguous floats at `addr`, taken from either a `{x,y,z}` table or three scalars; returns true on success, or false with the gating reason when the write cap is denied. |
| `protect` | `mem.protect(...: any) -> boolean,string?` | safe | Policy refusal; page-protection changes from Lua are disabled. Returns false (and a reason once the mem.write capability is granted). |
| `revert` | `mem.revert(...: any) -> boolean,string?` | safe | Policy refusal; script write-revert is disabled. Returns false (and a reason once the mem.write capability is granted). |
| `xref_scan` | `mem.xref_scan(...: any) -> nil,string?` | safe | Policy refusal; built-in xref scanning is disabled. Returns nil (and a reason once the mem capability is granted) — use read_bytes with a Lua-side disassembler. |
| `read_bytes` | `mem.read_bytes(address: integer, len: integer) -> string\|nil` | safe | Returns len bytes read from the given address as a Lua string, gated by the memory-read capability; returns an empty string when len <= 0 and nil plus an error reason when len exceeds the 1 MB per-call cap or the gated read faults. |
| `sig_scan` | `mem.sig_scan(module: string, pattern: string) -> integer\|nil` | safe | Alias of `mem.pattern_scan`: IDA-style byte-pattern scan over the named module, gated by the read capability and limited to the native module allowlist; returns the hit address as a lightuserdata, or nil plus an error when the module is not allowlisted/loaded, the region fails the scan check, or the scan faults mid-walk. |
| `read_color` | `mem.read_color(addr: integer) -> table\|nil` | safe | Reads 4 bytes at `addr` and returns a table `{r,g,b,a}` of 0–255 ints; requires the read capability and returns a failure stub if the gated read is refused. |
| `snapshot` | `mem.snapshot(...: any) -> any` | safe | Refusal stub: errors with "memory.snapshot: script write-snapshotting is disabled." |

### hooks

`namespace` · tier `privileged` — Function hooking (vmt / detour).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `vmt` | `hooks.vmt(instance: integer, slot_index: integer, detour: fun(args:table):any) -> HookHandle\|nil` | privileged | Installs a VMT hook on the given object instance at a vtable slot (0..512): clones the vtable, swaps the slot to an internal trampoline that dispatches to the Lua function, and returns a HookHandle; returns nil when the hooks capability is denied, the slot budget (128 live hooks) is exhausted, or the instance/vtable addresses do not pass the memory gate. |
| `detour` | `hooks.detour(target_addr: integer, detour: fun(args:table):any) -> HookHandle\|nil` | privileged | Installs an inline detour at the given function address, routing it through an internal trampoline that calls the Lua function (up to 6 integer args) and returns a HookHandle. The page must be committed and executable and the hooks capability granted; returns nil when the slot budget (128) is exhausted or install fails. Original bytes are snapshotted for host-driven revert. |
| `subscribe` | `hooks.subscribe(hook: string, handler: function) -> (string\|nil, integer)` | privileged | callback.add on the Lua channel behind a hook name; returns the channel and the callback id (nil, 0 without a function). A name list_subscribable does not list raises an error. FrameStageNotify maps to post_framestage, OnHeroKilled to hero_killed, OnFireBullets and OnBulletCreate to bullet_create. |
| `unsubscribe` | `hooks.unsubscribe(hook: string, id: integer) -> boolean` | privileged | callback.remove of a subscribe id on the hook's channel. |
| `list_subscribable` | `hooks.list_subscribable() -> table[]` | privileged | Every hook name subscribe accepts, as { hook, channel } rows (14 rows). |
| `is_subscribable` | `hooks.is_subscribable(hook: string) -> boolean` | privileged | True when subscribe accepts the name. |
| `channel_for` | `hooks.channel_for(hook: string) -> string\|nil` | privileged | The channel subscribe would use; nil for a name it rejects. |
| `count_by_module` | `hooks.count_by_module(module: string?) -> integer` | safe | Counts registered hooks whose target module matches the given name (empty string matches hooks with no module). |
| `iat` | `hooks.iat(...: any) -> boolean,string` | safe | Refusal stub: returns `false, reason` — IAT patching from Lua is disabled by policy. |
| `summary` | `hooks.summary() -> table` | safe | Returns `{ total, installed, latent, by_kind = { vmt, detour, iat, eat, callback, overlay } }` with counts across the hook registry. |
| `count_installed` | `hooks.count_installed() -> integer` | safe | Returns the number of DLL hooks that are currently live (installed). |
| `install` | `hooks.install(...: any) -> nil` | safe | Policy refusal: dynamic installation on the DLL's own hook table is disabled; raises a Lua error directing callers to `hooks.detour` / `hooks.vmt` for script hooks. |
| `symbol_of` | `hooks.symbol_of(name: string) -> string\|nil` | safe | Returns the target symbol string of the named DLL hook, or nil if no such hook. |
| `disable` | `hooks.disable(...: any) -> any` | safe | Refusal stub: hook enable/disable state is owned by the DLL and cannot be toggled from Lua. |
| `installed_names` | `hooks.installed_names() -> table` | safe | Returns an array of names of hooks currently installed and live. |
| `uninstall` | `hooks.uninstall(...: any) -> any` | safe | Refusal stub: statically-declared DLL hooks cannot be uninstalled from Lua; remove script-owned hooks via `handle:remove()`. |
| `dump` | `hooks.dump(...: any) -> any` | safe | Refusal stub: raw hook-table dump is not exposed to Lua. |
| `is_disabled` | `hooks.is_disabled(name: string) -> boolean` | safe | True when a hook by that name exists and is currently latent (installed but inactive). |
| `version` | `hooks.version() -> string` | safe | Returns the hook-table version string (`avalanche.hooks.v3`). |
| `eat` | `hooks.eat(...): (boolean, string: any)` | safe | Refusal stub: Export Address Table patching from Lua is disabled by policy. Returns false and the refusal reason. |
| `is_installed` | `hooks.is_installed(name: string) -> boolean` | safe | True if the named DLL hook record exists, is installed, and is not currently latent/disabled. |
| `enable` | `hooks.enable(...: any) -> nil` | safe | Refusal binding: errors with "hooks.enable: hook enable/disable state is owned by the DLL, not by Lua scripts." |
| `latent_names` | `hooks.latent_names() -> table` | safe | Returns an array of hook names from the DLL registry whose latent flag is set (hooks declared but not yet installed). |
| `enumerate` | `hooks.enumerate() -> table` | safe | Returns an array of records describing every registered engine hook. |
| `list` | `hooks.list() -> table` | safe | Returns an array of the registered engine hook names. |
| `fire_count` | `hooks.fire_count(channel: string) -> integer` | safe | Number of times the given hook channel has fired since the last `reset_fire_counts`; 0 if the channel name is unknown. |
| `module_of` | `hooks.module_of(name: string) -> string\|nil` | safe | Target module name recorded for the hook `name`, or nil if no such hook is registered. |
| `fire_counts` | `hooks.fire_counts() -> table` | safe | Returns a map {channel_name = fires_since_last_reset} for every subscribable hook channel. |
| `reset_fire_counts` | `hooks.reset_fire_counts() -> boolean` | safe | Snapshots the current source-call totals as the new baseline so subsequent hooks.fire_count/fire_counts read zero; always returns true. |
| `by_kind` | `hooks.by_kind(kind: string) -> table` | safe | Returns the names of installed hooks whose kind string equals `kind`. |
| `get_hook_type` | `hooks.get_hook_type(name: string) -> string\|nil` | safe | Returns the kind string (e.g. `"detour"`, `"vmt"`) of the named hook, or nil if no such hook exists. |
| `restore` | `hooks.restore(...: any) -> nil` | safe | Disabled by policy: errors with a refusal message explaining that internal hook-state restore is not exposed to Lua. |
| `by_module` | `hooks.by_module(module: string) -> table` | safe | Returns an array of registered hook names whose target_module matches the given module exactly. |
| `get_hooked_address` | `hooks.get_hooked_address(name: string) -> integer\|nil` | safe | Returns the installed virtual address for the named hook, or nil when the installer is not live. |
| `revert_all` | `hooks.revert_all() -> nil, string` | safe | Refusal stub: process-wide hook revert is host-owned, so this returns a policy message instead of acting. Use handle:remove() on your own handles. |
| `call_original` | `hooks.call_original(...: any) -> nil\|boolean, string\|nil` | safe | Refusal stub: dynamic `call_original` is not exposed; returns false (or nil without the capability) and the message steering callers to `handle:call_original(a1,...,a6)` on the HookHandle. |
| `get_info` | `hooks.get_info(name: string) -> table\|nil` | safe | Returns the static hook record (name, module, kind, address, etc.) for `name`, or `nil` if no such hook is registered. |
| `revert_script` | `hooks.revert_script(...: any) -> nil\|boolean, string\|nil` | safe | Refusal stub: cross-script bulk revert is not exposed; returns false (or nil without the capability) and the message directing callers to `handle:remove()` on their own handles. |
| `chain_after` | `hooks.chain_after(...: any) -> nil,string` | safe | Refusal stub: user-defined post-hooks are not exposed; returns nil plus a reason pointing at callback.after_* subscriptions. |
| `get_original` | `hooks.get_original(name: string?) -> nil,string` | safe | Refusal stub: exposing DLL-owned trampolines is disabled; returns nil plus a reason suggesting handle:call_original() on your own hook. |
| `set_break_on` | `hooks.set_break_on(...: any) -> nil,string` | safe | Refusal stub: script-driven hook debugger breakpoints are not exposed; returns nil plus a reason. |
| `chain_before` | `hooks.chain_before(...: any) -> boolean,string?` | safe | Policy refusal; returns false (and a reason once the capability is granted) because user-defined pre-hooks are not exposed. Use callback.before_* subscriptions. |
| `get_owner` | `hooks.get_owner() -> string` | safe | Returns the constant owner tag "avalanche.core" for DLL-owned static hooks. |
| `set_owner` | `hooks.set_owner(...: any) -> boolean,string?` | safe | Policy refusal; attribution is fixed at install time and cannot be reassigned from Lua. |
| `count` | `hooks.count() -> integer` | safe | Returns the total number of rows in the DLL's static hook registry (installed or not). |
| `get_priority` | `hooks.get_priority(name: string) -> integer\|nil` | safe | Returns the registry index of the named hook (its fixed install-order priority), or nil if no hook with that name exists. |
| `set_priority` | `hooks.set_priority(...: any) -> boolean,string` | safe | Policy refusal: always returns false and the message "hooks.set_priority: hook ordering is static and not user-configurable." |
| `count_by_kind` | `hooks.count_by_kind(kind: string) -> integer` | safe | Counts hooks whose kind string matches the argument. |
| `get_stats` | `hooks.get_stats(name: string) -> table\|nil` | safe | Returns runtime stats for the named hook — `count`, `total_ns`, `avg_ns`, `max_ns`, `rejections`, `available` — or nil if the hook is unknown. |
| `snapshot` | `hooks.snapshot(...: any) -> any` | safe | Refusal stub: errors with "hooks.snapshot: internal hook state snapshots are not exposed to Lua." |

### HookHandle

`usertype` · tier `privileged` — Handle returned by hooks.vmt / hooks.detour.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `remove` | `:remove() -> nil` | privileged | Uninstalls this script-owned hook: deactivates the slot, drops the Lua detour function, uninstalls the VMT clone when the hook is a VMT one, and returns the slot to the free list. |
| `call_original` | `:call_original(...: integer) -> integer\|nil` | privileged | Invokes the stored original function (through the detour trampoline or saved vtable entry) with up to six numeric arguments and returns its 64-bit result as a number; returns nil when the slot has no original or has already been removed. The native call runs under an SEH guard. |
| `is_active` | `:is_active() -> boolean` | privileged | Returns true if this handle's slot is still installed and dispatching to the Lua function, false after remove() or if the slot index is invalid. |

### Schema

`namespace` · tier `safe` — Source2 schema access (enums / field offsets).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `enum` | `Schema.enum(name: string) -> table` | safe | Looks up the named schema enum and returns a table mapping each enumerator name to its integer value; returns an empty table when the enum is unknown. |
| `fields` | `Schema.fields(class: string) -> table` | safe | Returns an array of field names for the given schema class via live enumeration; requires the schema.raw_read capability and returns an empty table when the capability is denied or the class is unknown. |
| `offset` | `Schema.offset(class: string, field: string) -> integer` | safe | Returns the byte offset of (class, field) resolved against the live schema, or nil when the field is not found. Requires the schema.raw_read capability. |
| `field_info` | `Schema.field_info(class: string, field: string) -> table\|nil` | safe | Field metadata { offset, type, ... }. |
| `read` | `Schema.read(target: integer\|PlayerPawn\|Ability\|Entity, class: string, field: string) -> any\|nil` | safe | Read a schema field off an entity. Pass the entity/pawn/ability object, or a raw address the engine handed out (ent:get_address()). Arbitrary addresses return nil unless the script is trusted. |
| `field_hash` | `Schema.field_hash(cls: string, field: string) -> integer` | safe | FNV-1a hash of `"class::field"` used as the schema cache key; returns 0 when either argument is empty or the schema cap is denied. |
| `field_offset` | `Schema.field_offset(class: string, field: string) -> integer\|nil` | safe | Alias of `Schema.field`. Returns the resolved byte offset of `field` on `class`; nil when the schema cap is denied, arguments are empty, or the lookup fails. |
| `field_type` | `Schema.field_type(class_name: string, field: string) -> string\|nil` | safe | Alias of `schema.get_field_type`: returns the schema field's declared type name, or nil when the field is not registered. |
| `find_class` | `Schema.find_class(name: string) -> table\|nil` | safe | Returns a descriptor table `{name, size?, has_chain, field_count}` for `name` if it exists in the live schema or the known-class table, else nil. |
| `available` | `Schema.available() -> boolean` | safe | True when the schema subsystem has been initialized. |
| `get_class_chain` | `Schema.get_class_chain(cls: string) -> table` | safe | Returns the inheritance chain for cls as an array of class names, falling back to the legacy static table and finally to just [cls]. Returns an empty table when the schema.raw_read capability is denied. |
| `cache_stats` | `Schema.cache_stats() -> table` | safe | Returns a table with the schema offset-cache entries count and a placeholder capacity of 0. |
| `get_class_size` | `Schema.get_class_size(class_name: string) -> integer\|nil` | safe | Alias of Schema.class_size: returns the schema class's instance size in bytes, falling back to the known-class size hint; nil when neither is available or the schema.raw_read capability is denied. |
| `class_chain` | `Schema.class_chain(cls: string) -> table` | safe | Alias of `Schema.get_class_chain`; returns an array walking from `cls` up through its base classes. Needs the `schema.raw_read` capability — returns an empty table otherwise. |
| `get_field_type` | `Schema.get_field_type(cls: string, field: string) -> string` | safe | Returns the schema type name of `cls::field`; `"unknown"` when the field cannot be resolved or the `schema.raw_read` capability is denied. |
| `class_hash` | `Schema.class_hash(class_name: string) -> integer` | safe | FNV-1a hash of `class_name`; returns 0 if the caller lacks the `schema.raw_read` capability or `class_name` is empty. |
| `has` | `Schema.has(class_name: string) -> boolean` | safe | True if `class_name` is a live schema class or a known baked-in class. |
| `class_size` | `Schema.class_size(class_name: string) -> integer\|nil` | safe | Returns the schema class size in bytes (live, else the known-class hint); nil if the schema.raw_read capability is denied or the class is unknown. |
| `has_class` | `Schema.has_class(class_name: string) -> boolean` | safe | Alias of `Schema.has`; true when the class is present in the live schema or the known-class table. |
| `classes` | `Schema.classes() -> table` | safe | Returns an array of every live schema class name. |
| `has_field` | `Schema.has_field(class: string, field: string) -> boolean` | safe | True iff the given schema class contains the named field. |
| `classify_type` | `Schema.classify_type(type_name: string) -> string` | safe | Returns a short name for the schema field kind of the given type (e.g. `Int32`, `Vector3`, `UtlVector`, `Unknown`). Requires the `schema.raw_read` capability. |
| `parse_inline_array` | `Schema.parse_inline_array(type_name: string) -> string\|nil, integer\|nil` | safe | Parses an inline-array schema type and returns `(element_type, count)`; returns `(nil, nil)` on non-matching types or without the `schema.raw_read` capability. |
| `count` | `Schema.count() -> integer` | safe | Returns the number of live schema classes, or the compiled known-class count when the live schema reports none. |
| `parse_utl_vector` | `Schema.parse_utl_vector(type_name: string) -> string\|nil` | safe | Parses a `CUtlVector<T>`-style type name and returns the element type string, or nil if parsing fails or the `schema.raw_read` capability is not granted. |
| `dump_class` | `Schema.dump_class(cls: string) -> table\|nil` | safe | Returns a `{field_name = offset}` table for every field known on the class; nil without the `schema.raw_read` capability or for an empty class name. |
| `pointee_type` | `Schema.pointee_type(type_name: string) -> string\|nil` | safe | Parses a pointer type string and returns the pointee type name; nil without the `schema.raw_read` capability or when the input is not a pointer. |
| `enumerate_classes` | `Schema.enumerate_classes() -> table` | safe | Alias of `Schema.classes`; returns an array of all live schema class names (falls back to the known-class table when the live enumerator is empty). |
| `reset_cache` | `Schema.reset_cache() -> boolean,string` | safe | Policy refusal; returns false and "schema.reset_cache: offset cache is DLL-owned; scripts cannot flush it." |
| `enumerate_fields` | `Schema.enumerate_fields(cls: string) -> table` | safe | Returns an array of the field names on the schema class `cls`; gated by the `schema.raw_read` capability (returns an empty table when denied). |
| `set_field_offset` | `Schema.set_field_offset(...: any) -> boolean,string` | safe | Policy refusal: always returns false and the message "schema.set_field_offset: schema offsets are read-only from Lua." |
| `field` | `Schema.field(cls: string, field: string) -> integer\|nil` | safe | Resolves the byte offset of `cls.field` from the schema; nil when the inputs are empty, the capability is missing, or the field is unknown. |
| `version` | `Schema.version() -> string` | safe | Returns the schema layer version string (`avalanche.schema.v3`). |

### prediction

`namespace` · tier `safe` — Projectile / movement prediction over the cheat's solvers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `projectile` | `prediction.projectile(ability_or_params: any, ...) -> table\|nil` | safe | With a radius (params.radius or the ability's), a lead whose path the map mesh blocks returns nil. |
| `aim_angles` | `prediction.aim_angles(eye: Vector3, target_pos: Vector3, target_vel: Vector3, speed: number, gravity: number, target_gravity?: number) -> table\|nil` | safe | target_gravity (the target's fall, units/s^2) defaults to sv_gravity, 800 on standard servers. |
| `launch_position` | `prediction.launch_position(ability: Ability) -> Vector3\|nil` | safe | Returns the ability's current launch (muzzle) world position via AbilityLaunch::TryGetLaunchPosition; nil without an ability or when the position is not finite. |
| `launch_angle` | `prediction.launch_angle(ability: Ability) -> table\|nil` | safe | Returns the ability's current launch angles as { pitch, yaw, roll } via AbilityLaunch::TryGetLaunchAngle; nil without an ability or when none is available. |
| `fastest_projectile` | `prediction.fastest_projectile() -> table\|nil` | safe | Reads the fastest sampled projectile from AbilityLaunch and returns { valid, speed, radius, init_vel, cur_vel, count }; nil when no sample is available. |
| `simulate_physics` | `prediction.simulate_physics(start_pos: Vector3, start_vel: Vector3, gravity?: number, time: number, step?: number) -> table\|nil` | safe | Moves a point under gravity (default sv_gravity) for `time` s in `step` steps (default 1/64), sweeping each step against the map collision mesh (radius 18) and sliding along what it hits. Returns { end_pos, end_vel, hit_wall, hit_floor, hit_ceiling, collisions, path }. Nothing collides while the map mesh is not built. |
| `gravity` | `prediction.gravity(pawn?: PlayerPawn, distance?: number) -> number\|nil` | safe | Bullet drop of the pawn's current primary weapon in units/s^2 (m_flBulletGravityScale x sv_gravity, 800 on standard servers; 0 = no drop). The local pawn's comes from the per-tick bullet data the aimbot leads with (re-read on a weapon change and every second); another pawn's is read live. With a distance in units: the constant gravity that drops a straight shot that long as far as the weapon's gravity-by-distance curve does (Rat King's curve: no drop to ~1500 units, a 0.8 scale at 3000, so gravity(nil, 3000) is about 45); without one, the base scale. Defaults to the local pawn; nil when there is no pawn or its weapon data cannot be read. |
| `trajectory_blocked` | `prediction.trajectory_blocked(from: Vector3, to: Vector3, time?: number, gravity?: number, radius?: number, segments?: integer, near_impact_skip?: number) -> boolean` | safe | true when the map mesh blocks the shot before the last near_impact_skip of its path; arced in `segments` chords when gravity and time are set; swept with `radius` (default 5). false without a positive time; segments defaults to 4 and near_impact_skip is a 0-1 fraction of the path. |
| `simulate` | `prediction.simulate(pawn: PlayerPawn, ticks?: integer) -> Vector3[]` | safe | the pawn's path over `ticks` 1/64 s steps from this tick's origin and velocity, through simulate_physics' mesh sweep. ticks defaults to 32; empty when the frame does not hold the pawn. |
| `ballistic` | `prediction.ballistic(from: Vector3, to: Vector3, speed: number?, gravity: number?) -> table` | safe | Solves a stationary ballistic shot and returns a solution table `{valid, pitch, yaw, roll, time, hit_time, pos, aim}`; result is invalid when speed <= 0 or either point fails to read as a Vector3. |
| `moving_ballistic` | `prediction.moving_ballistic(from: Vector3, to: Vector3, vel: Vector3, speed: number, gravity: number?, target_gravity: number?) -> table` | safe | Runs the ballistic solver against a target with velocity vel. Returns an empty solution table when any vector argument fails to parse or speed <= 0. |
| `predict` | `prediction.predict(origin: Vector3, target_pos: Vector3, target_vel: Vector3, speed: number, bullet_gravity: number, target_gravity: number) -> table` | safe | Solves a general ballistic prediction given shooter origin, target position and velocity, bullet speed and both bullet and target gravities, and returns the solution table; a zero/missing speed or any missing vector returns an empty solution. |
| `predict_position` | `prediction.predict_position(pos: Vector3, vel: Vector3, dt: number, collide: boolean\|nil, gravity: number\|nil) -> Vector3` | safe | Advances `pos` along `vel` for `dt` seconds using the prediction system, optionally resolving collisions and applying `gravity`; returns the predicted point, zero vector on bad input. |
| `solve_moving_target` | `prediction.solve_moving_target(from: Vector3, target: Vector3, target_velocity: Vector3, speed: number, gravity: number) -> table` | safe | Solves a ballistic lead against a moving target and returns the resulting solution table (hit position, angles, time, success flag); empty solution if any vector argument is unreadable. |

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
| `bin` | `log.bin(v: integer\|boolean) -> string` | safe | Formats an integer (or boolean coerced to 0/1) as a `0b…` binary string; non-numeric input gives `0b0`. |
| `info_once` | `log.info_once(key: string, msg: string)` | safe | No-op stub reserved for one-shot info logging. |
| `channel_get` | `log.channel_get(name: string) -> integer` | safe | Returns the current log level of the named channel (0..5); returns 2 (INFO) when the name is missing or the channel is not registered. |
| `kv` | `log.kv(...: any) -> nil` | safe | No-op stub reserved for structured key/value log emission. |
| `channel_names` | `log.channel_names() -> table` | safe | Returns an array of registered log channel names; empty table if no channels table is set up. |
| `level_of` | `log.level_of(severity: string) -> integer` | safe | Maps a severity string's first letter to its numeric level: t=0 (trace), d=1 (debug), i=2 (info), w=3 (warn), e=4 (error), f=5 (fatal); defaults to 2. |
| `channel_set` | `log.channel_set(name: string, level: integer) -> integer` | safe | Writes `log.channels[name] = level` (clamped to [0, 5]) and returns the clamped level; no-op if `log` or `log.channels` isn't a table. |
| `mark` | `log.mark(label: string)` | safe | No-op stub for inserting a labeled marker into the log stream. |
| `clear_once_keys` | `log.clear_once_keys()` | safe | No-op stub; present so once-key callers do not error. |
| `now_ms` | `log.now_ms() -> number` | safe | Returns the current monotonic kusd tick converted to milliseconds. |
| `clear_sink` | `log.clear_sink(name: string\|nil) -> boolean` | safe | Clears a log sink: with a non-empty name removes that one sink and returns whether it existed; with no name (or an empty one) removes every sink and returns true. |
| `now_s` | `log.now_s() -> number` | safe | Returns the current kusd tick as seconds (100ns ticks divided by 1e7). |
| `counter_dec` | `log.counter_dec(name: string, ...: any) -> nil` | safe | No-op stub retained for script compatibility. |
| `scope_begin` | `log.scope_begin(name: string) -> nil` | safe | No-op stub retained for script compatibility. |
| `counter_inc` | `log.counter_inc(name: string, ...: any)` | safe | No-op stub; the structured-logging counter sink is not wired on this build. |
| `scope_end` | `log.scope_end(name: string)` | safe | No-op stub; the structured-logging scope sink is not wired on this build. |
| `debug_once` | `log.debug_once(key: string, msg: string)` | safe | No-op stub; retained for API shape only. |
| `set_level` | `log.set_level(level: integer)` | safe | Sets the global log severity threshold (clamped to 0..5): 0=trace, 1=debug, 2=info, 3=warn, 4=error, 5=fatal. |
| `event` | `log.event(name: string, ...: any) -> nil` | safe | No-op stub for structured event logging. |
| `set_sink` | `log.set_sink(name_or_fn: any, enabled_or_fn: any?) -> boolean` | safe | Registers or toggles a named log sink; passing a function as the first argument registers it under the sink name `lua`, a boolean second argument toggles the sink on/off. Returns true if the sink entry was stored. |
| `format` | `log.format(fmt: string, ...: any) -> string` | safe | Thin wrapper around string.format: formats and returns the result, or an empty string if no format arg is given. |
| `tail` | `log.tail(n: integer) -> table` | safe | Stub returning a one-element table with the string "[log.tail] stub"; no in-memory log is retained for scripts. |
| `gauge_set` | `log.gauge_set(name: string, value: number)` | safe | No-op stub. |
| `tail_cap` | `log.tail_cap() -> integer` | safe | Returns the fixed tail-buffer cap (256). |
| `get_level` | `log.get_level() -> integer` | safe | Returns the current global log level (0 trace .. 5 fatal) via an interlocked read. |
| `tail_size` | `log.tail_size() -> integer` | safe | Stub that always returns 1; the in-memory log tail is not surfaced to Lua. |
| `has_channel` | `log.has_channel(name: string) -> boolean` | safe | Returns true when the DLL's log-channel table exposes an entry for name. |
| `timer_lap` | `log.timer_lap(label: string)` | safe | No-op stub taking a label string; present for API parity with log timing helpers. |
| `note` | `log.note(...: any) -> nil` | safe | Alias of `log.warn`. |
| `has_sink` | `log.has_sink(name: string\|nil) -> boolean` | safe | With no string argument, returns whether any log sink is active; with a non-empty name, returns whether a sink is registered for that script name. |
| `vec_str` | `log.vec_str(v: Vector3) -> string` | safe | Formats a Vector3 as a short string using two-decimal fixed-point for each component (built with a 96-byte scratch buffer, no scientific notation). |
| `hex` | `log.hex(v: integer\|boolean) -> string` | safe | Formats the value as a `0x`-prefixed lowercase hex string; non-numeric/boolean input returns `"0x0"`. |
| `warn_once` | `log.warn_once(key: string, msg: string)` | safe | No-op stub (dedup-by-key warn is unimplemented). |

### lua_convar_t

`usertype` · tier `safe` — Read-only Source2 ConVar value handle (convar.<name>).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `float` | `:float() -> number` | safe | Returns the convar's current value as a float, reading it through the SDK's typed convar accessor; returns 0 when the ref is null or the read fails. |
| `int` | `:int() -> integer` | safe | Returns the convar's current value as an int32, reading it through the SDK's typed convar accessor; returns 0 when the ref is null or the read fails. |
| `bool` | `:bool() -> boolean` | safe | Returns true when the convar's float value is non-zero (reads the convar through the SDK float accessor); returns false otherwise. |
| `string` | `:string() -> string` | safe | The value as text: a string convar's value (at most 1023 bytes), a number as text (integers and bools as an integer, floats with %g); "" for other kinds (colors, vectors) or an invalid convar. |
| `get_string` | `:get_string() -> string` | safe | The value as text: a string convar's value (at most 1023 bytes), a number as text (integers and bools as an integer, floats with %g); "" for other kinds (colors, vectors) or an invalid convar. |
| `get_address` | `:get_address() -> integer\|nil` | safe | The ConVar's address; nil without the "schema.raw_read" capability (trusted scripts only). |
| `name_of` | `:name_of() -> string` | safe | Returns the name used to look up this convar. |
| `valid` | `:valid() -> boolean` | safe | Returns true when the convar reference is non-null. |
| `get_bool` | `:get_bool() -> boolean` | safe | Reads the bound ConVar as a boolean. |
| `get_float` | `:get_float() -> number` | safe | Returns the ConVar's current value as a float. |
| `get_int` | `:get_int() -> integer` | safe | Returns the ConVar's integer value (via AsInt). |
| `get_name` | `:get_name() -> string` | safe | Returns the convar name the wrapper was created with. |
| `is_valid` | `:is_valid() -> boolean` | safe | True when the wrapped ConVar reference is non-null. |

### lua_target_selection_wrapper_t

`usertype` · tier `safe` — Self-contained filter+scoring target selector.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `set_filter` | `:set_filter(predicate: fun(entity:PlayerPawn):boolean) -> nil` | safe | Stores `fn` as the predicate called with each candidate pawn during run(); only candidates for which it returns truthy are scored. |
| `add_criterion` | `:add_criterion(scorer: fun(entity:PlayerPawn):number, weight: number) -> nil` | safe | Appends a scoring function with the given weight; during run() each criterion is called with the candidate pawn and its numeric return is added, multiplied by the weight, to that candidate's score. |
| `set_flag` | `:set_flag(value: boolean) -> nil` | safe | Writes the wrapper's user bool slot. |
| `set_int` | `:set_int(value: integer) -> nil` | safe | Writes the wrapper's user integer slot. |
| `set_scalar` | `:set_scalar(value: number) -> nil` | safe | Writes the wrapper's user float slot. |
| `set_mode` | `:set_mode(mode: string) -> nil` | safe | Writes the wrapper's user mode integer. |
| `set_target` | `:set_target(target: PlayerPawn) -> nil` | safe | Writes the selection's target CHandle. |
| `configure` | `:configure(cfg: table) -> nil` | safe | Bulk-applies a table of fields (filter, mode, flag, int, scalar, target, priority, source, confidence, reason, and a criteria array of { fn, weight } rows); each field is written only when present and of the expected type. |
| `get_config` | `:get_config() -> table` | safe | Returns the current configuration as a table (filter, mode, flag, int, scalar, target, priority, source, confidence, reason, and the criteria array of { fn, weight } rows). |
| `run` | `:run() -> PlayerPawn\|nil` | safe | Collects all players, filters them through the stored filter, scores the survivors by summing weighted criterion returns, writes the best candidate's handle into the selection, and returns that pawn (nil when no candidate passed). |
| `get_index` | `:get_index() -> integer` | safe | Entity index of the current target, or -1 if the stored handle is not valid. |
| `get_int` | `:get_int() -> integer` | safe | Returns the stored integer value on the target-selection wrapper; 0 if the wrapper is null. |
| `get_mode` | `:get_mode() -> integer` | safe | Returns the stored mode integer; 0 when the wrapper is null. |
| `get_priority` | `:get_priority() -> integer` | safe | Returns the wrapper's cached priority value. |
| `get_reason` | `:get_reason() -> string` | safe | Returns the target's reasonTag string. |
| `get_scalar` | `:get_scalar() -> number` | safe | Returns the wrapper's scalar field (0 if self is nil). |
| `get_source` | `:get_source() -> integer` | safe | Returns the integer source tag that identifies which selector produced this target. |
| `get_target` | `:get_target() -> CHandle` | safe | Current target handle stored on the selection wrapper. |
| `is_valid` | `:is_valid() -> boolean` | safe | True when the wrapped target handle is valid. |
| `outweighs` | `:outweighs(other: lua_target_selection_wrapper_t) -> boolean` | safe | True when `self` ranks above `other`: higher priority first, then higher confidence, then lower source index as the tiebreak. |
| `set_confidence` | `:set_confidence(confidence: number)` | safe | Sets the selection's confidence, clamped into [0, 1]. |
| `set_handle` | `:set_handle(h: integer)` | safe | Overwrites the selection's target handle with `h`. |
| `clear_criteria` | `:clear_criteria()` | safe | Removes every scoring criterion previously attached with `add_criterion`. |
| `set_priority` | `:set_priority(priority: integer)` | safe | Sets the integer priority used when comparing selections (higher wins in `outweighs`). |
| `get_confidence` | `:get_confidence() -> number` | safe | Returns the selection's confidence field (0..1). |
| `set_reason` | `:set_reason(reason: string)` | safe | Overwrites the selection's reason tag with the given string. |
| `get_flag` | `:get_flag() -> boolean` | safe | Returns the user-settable `flag` field on the selection scratch slot, or false when the wrapper is detached. |
| `set_source` | `:set_source(source: integer)` | safe | Stores `source` as the selection's source tag, used as a tiebreaker in `outweighs`. |
| `get_handle` | `:get_handle() -> CHandle` | safe | Returns the stored target CHandle. |
| `valid` | `:valid() -> boolean` | safe | True when the stored target CHandle is a valid entity reference. |

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
| `CountByPath` | `particle.CountByPath(path: string) -> integer` | safe | Number of script-tracked particles currently alive for the given .vpcf path. |
| `SetAlpha255` | `particle.SetAlpha255(handle: integer, a: integer)` | safe | Sets a particle's alpha from a 0-255 byte (clamped and rescaled to 0-1). |
| `destroy_all` | `particle.destroy_all() -> integer` | safe | Alias of `particle.DestroyAll` — destroys every tracked particle and returns how many were released. |
| `set_origin` | `particle.set_origin(handle: integer, origin: Vector3)` | safe | Alias of `particle.SetOrigin` — repositions a tracked particle to the given world origin. |
| `Create` | `particle.Create(path: string, attach_type: string\|nil, entity_idx: integer\|nil) -> integer` | safe | Allocates a particle instance (defaulting `attach_type` to `"point"` and entity index to -1), attributes it to the calling script, and returns the particle handle (0 on failure). |
| `SetControlPoint` | `particle.SetControlPoint(handle: integer, cp_idx: integer, pos: Vector3) -> nil` | safe | Sets control point `cp_idx` of the particle to `pos` via `SetControlPointPosition`. |
| `destroy_by_path` | `particle.destroy_by_path(path: string) -> integer` | safe | Destroys every live particle whose source path matches and returns how many were destroyed. |
| `set_origin_v` | `particle.set_origin_v(handle: integer, pos: any) -> nil` | safe | Reads a Vec3-like value from `pos` and applies it as the particle's origin; no-op if the value cannot be read as a vector. |
| `CreateAt` | `particle.CreateAt(path: string, origin: Vector3, attachType: string\|nil, entityIdx: integer\|nil) -> integer` | safe | Spawns a particle `path` at `origin`, defaulting the attach type to "point" and `entityIdx` to -1; returns the new particle handle (or <=0 on failure) and sets its control-point origin on success. |
| `SetControlPointEnt` | `particle.SetControlPointEnt(handle: integer, cpIdx: integer, entity: integer, attachType: string\|nil)` | safe | Attaches control point `cpIdx` of particle `handle` to `entity`; `attachType` is accepted but ignored. |
| `enumerate_active` | `particle.enumerate_active() -> table` | safe | Alias of `particle.EnumerateActive`. |
| `set_tint` | `particle.set_tint(handle: integer, r: number, g: number, b: number)` | safe | Alias of `particle.SetTint`. |
| `Destroy` | `particle.Destroy(handle: integer, immediate: boolean?) -> boolean` | safe | Destroys the particle with the given handle; `immediate` forces synchronous teardown. Returns true on success. |
| `SetControlPointForward` | `particle.SetControlPointForward(handle: integer, cp_index: integer, forward: Vector3)` | safe | Sets the forward direction of control-point `cp_index` on the particle. |
| `enumerate_by_path` | `particle.enumerate_by_path(path: string) -> table` | safe | Alias of `particle.EnumerateByPath`: returns an array of active particle handles created with the given path. |
| `tick` | `particle.tick()` | safe | Alias of `particle.Tick`: advances the internal particle tick counter. |
| `DestroyAll` | `particle.DestroyAll() -> integer` | safe | Destroys every particle registered by Lua and returns the count removed. |
| `SetControlPointOrientation` | `particle.SetControlPointOrientation(handle: integer, cp: integer, fwd: Vector3, right: Vector3, up: Vector3)` | safe | Sets the forward axis of control point cp from fwd; the right and up arguments are accepted for API compatibility but ignored. |
| `get_control_point` | `particle.get_control_point(handle: integer, cp: integer) -> Vector3` | safe | Alias of `particle.GetControlPoint`. |
| `DestroyByPath` | `particle.DestroyByPath(path: string) -> integer` | safe | Destroys every live particle whose source path matches path and returns the number destroyed. |
| `SetControlPointV` | `particle.SetControlPointV(handle: integer, cp: integer, pos: any)` | safe | Reads a Vector3 (or vec-like table) from the third arg and sets control point cp of the particle to that position; no-op when the arg does not parse as a Vector3. |
| `get_info` | `particle.get_info(handle: integer) -> table` | safe | Alias of particle.GetInfo. |
| `EngineStatus` | `particle.EngineStatus() -> string` | safe | Returns a human-readable status string for the particle backend (either "particle backend wired" or an "unavailable" message). |
| `SetOrigin` | `particle.SetOrigin(handle: integer, origin: Vector3) -> nil` | safe | Sets the origin of the particle effect identified by `handle`. |
| `get_stats` | `particle.get_stats() -> table` | safe | Alias of `particle.GetStats`; returns a snapshot table of particle counters (`total_created`, `total_destroyed`, `total_set_calls`, `slot_count`, `tick_counter`, `engine_generation`, `alive_count`, `engine_alive_count`). |
| `EnumerateActive` | `particle.EnumerateActive() -> table` | safe | Array of script-side handles for every live tracked particle slot. |
| `SetOriginV` | `particle.SetOriginV(handle: integer, pos: Vector3\|table)` | safe | Sets the origin of the particle at `handle` to `pos`; a no-op if `pos` is not a readable 3-vector. |
| `is_active` | `particle.is_active(handle: integer) -> boolean` | safe | Alias of `particle.IsValid`. |
| `EnumerateByPath` | `particle.EnumerateByPath(path: string) -> table` | safe | Returns an array of active particle handles whose source path matches the given particle resource path. |
| `SetTint` | `particle.SetTint(handle: integer, r: number, g: number, b: number)` | safe | Sets the particle's RGB tint using floating-point channels (0..1). |
| `is_valid` | `particle.is_valid(handle: integer) -> boolean` | safe | Alias of `particle.IsValid`; true when the handle currently maps to a live particle slot. |
| `GetControlPoint` | `particle.GetControlPoint(handle: integer, cpIdx: integer) -> Vector3` | safe | Returns the particle's control-point position at index `cpIdx`. |
| `SetTint255` | `particle.SetTint255(handle: integer, r: integer, g: integer, b: integer) -> nil` | safe | Sets the particle tint from 0-255 R/G/B channels (clamped before being converted to float). |
| `set_alpha` | `particle.set_alpha(handle: integer, alpha: number) -> nil` | safe | Alias of `particle.SetAlpha`. |
| `GetInfo` | `particle.GetInfo(handle: integer) -> table` | safe | Returns a snapshot table for the particle slot: valid, path, attach_type, attached_entity, active, destroyed, frame_created, engine_idx, origin{x,y,z}, tint{r,g,b}, alpha. A missing slot yields `{valid=false}`. |
| `Tick` | `particle.Tick()` | safe | Advances the particle tick counter one step; the lowercase `tick` is the same function. |
| `set_color` | `particle.set_color(handle: integer, r: number, g: number, b: number)` | safe | Alias of `particle.SetTint`: sets the particle's RGB tint in 0..1 units. |
| `GetStats` | `particle.GetStats() -> table` | safe | Returns a snapshot of the particle manager counters (total_created, total_destroyed, total_set_calls, slot_count, tick_counter, engine_generation, alive_count, engine_alive_count). |
| `attach` | `particle.attach(handle: integer, attachType: string, entity: integer\|nil)` | safe | Alias of `particle.Attach`; attaches the particle to `attachType` on `entity` (defaults to -1 when omitted). |
| `set_control_point` | `particle.set_control_point(handle: integer, cpIdx: integer, v: Vector3)` | safe | Alias of `particle.SetControlPoint`; sets control-point `cpIdx` of particle `handle` to position `v`. |
| `IsActive` | `particle.IsActive(handle: integer) -> boolean` | safe | Returns true when `handle` refers to a currently live particle slot (same test as `IsValid`). |
| `count_active` | `particle.count_active() -> integer` | safe | Returns the number of script-spawned particles currently alive. |
| `set_control_point_ent` | `particle.set_control_point_ent(handle: integer, cp: integer, entity: integer, attachment: string?) -> nil` | safe | Attaches control point `cp` of the particle to the given entity handle; the attachment-name argument is accepted but ignored. |
| `IsEngineAvailable` | `particle.IsEngineAvailable() -> boolean` | safe | Returns true when the game's CGameParticleManager has been resolved. |
| `count_by_path` | `particle.count_by_path(path: string) -> integer` | safe | Returns the number of currently active particles whose effect path matches path. |
| `set_control_point_forward` | `particle.set_control_point_forward(handle: integer, cp: integer, fwd: Vector3)` | safe | Sets the forward direction of control point cp on the particle handle. |
| `Attach` | `particle.Attach(handle: integer, attachType: string, entity: integer\|nil)` | safe | Re-attaches an existing particle `handle` to the given attachment type and, when provided, entity index (defaulting to -1). |
| `IsValid` | `particle.IsValid(handle: integer) -> boolean` | safe | Returns whether the given particle handle still corresponds to a live particle entry. |
| `create` | `particle.create(path: string, attachType: string\|nil, entityIdx: integer\|nil) -> integer` | safe | Alias of `particle.Create`: allocates a particle from the resource at `path` with the given attachment type (default "point") and entity index (default -1); returns the new particle handle, or 0 on failure. |
| `set_control_point_orientation` | `particle.set_control_point_orientation(handle: integer, cpIdx: integer, forward: Vector3, right: Vector3, up: Vector3)` | safe | Alias of `particle.SetControlPointOrientation`: sets control point `cpIdx` on `handle` to the given forward vector; the `right` and `up` arguments are accepted for signature compatibility but ignored. |
| `CountActive` | `particle.CountActive() -> integer` | safe | Number of currently active script-owned particles. |
| `SetAlpha` | `particle.SetAlpha(handle: integer, a: number)` | safe | Sets the particle's alpha scalar (0–1 range). |
| `destroy` | `particle.destroy(handle: integer, immediate: boolean\|nil) -> boolean` | safe | Alias of `particle.Destroy`. |
| `set_control_point_v` | `particle.set_control_point_v(handle: integer, cp: integer, v: any)` | safe | Alias of `particle.SetControlPointV` — sets the control point from a value readable as a Vector3; silently drops if the value is not vec3-shaped. |

### ParticleHandle

`usertype` · tier `safe` — Chainable particle-effect handle returned by Particle.create / Particle.spawn.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `at` | `:at(cp: integer, v: Vector3) -> ParticleHandle` | safe | Sets control point `cp` of the live particle to a world-space Vector3 position; a no-op if the vector argument fails to parse or the handle's generation is stale. Returns self. |
| `attach` | `:attach(cp: integer, ent: any, attach_type?: integer, attach_point?: string) -> ParticleHandle` | safe | Attaches control point `cp` of the live particle to the given entity (pawn, ability, or integer handle) using the specified attachment type (defaults to ABSORIGIN_FOLLOW) and optional attachment-point name. Returns self. |
| `forward` | `:forward(cp: integer, dir: Vector3) -> ParticleHandle` | safe | Sets control point `cp`'s forward direction on the live particle to the given Vector3; a no-op if the vector is invalid or the handle is stale. Returns self. |
| `orientation` | `:orientation(cp: integer, ang: Vector3) -> ParticleHandle` | safe | Sets control point `cp`'s orientation angles on the live particle with the anchor fixed at (0,0,0); a no-op if the vector is invalid or the handle is stale. Returns self. |
| `activate` | `:activate() -> ParticleHandle` | safe | Activates (starts emitting) the handle's particle. Returns self. |
| `stop` | `:stop(hard?: boolean, play_end_cap?: boolean)` | safe | Stops the live particle; `hard` forces an immediate stop (default false) and `play_end_cap` plays the end-cap effect (default true). A no-op during map transitions or when the handle's generation has advanced. |
| `valid` | `:valid() -> boolean` | safe | Returns true if the handle's index is non-zero and its generation still matches the live particle system's current generation. |
| `index` | `:index() -> integer` | safe | Returns the raw particle index of the handle. |

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
| `proxy_url` | `http.proxy_url() -> string` | safe | Returns the configured HTTP proxy URL (empty string when none). |
| `request_async` | `http.request_async(method: string, url: string, body: string\|nil, callback: function\|nil, headers: table\|nil) -> integer` | safe | Submits an asynchronous HTTP request with the given method/url/body, optional completion callback and optional headers table; returns the submission id. |
| `reset_metrics` | `http.reset_metrics() -> boolean` | safe | Resets the HTTP metrics counters; returns false (no reset) when the caller is not trusted, true on success. |
| `set_max_concurrent` | `http.set_max_concurrent(n: integer?) -> boolean` | safe | Trusted-only: sets the global max concurrent HTTP request cap (clamped to [1, kMaxConcurrentCap]); returns false for untrusted callers. |
| `cancel` | `http.cancel(id: integer) -> boolean` | safe | Cancels the pending request with the given id when it is owned by the caller's script, dropping its callback and HTTP job. Returns true if the request was found and dropped. |
| `unescape_html` | `http.unescape_html(s: string) -> string` | safe | Decodes HTML entities in s and returns the decoded string. |
| `default_timeout_ms` | `http.default_timeout_ms() -> integer` | safe | Returns the default per-request timeout, in milliseconds, applied when a request table does not set one. |
| `url_decode` | `http.url_decode(s: string) -> string` | safe | Returns the percent-decoded form of s (empty string if omitted). |
| `enqueue_download` | `http.enqueue_download(url: string, path: string, cb: fun(...):any\|nil) -> integer` | safe | Submits an async GET for `url` and returns the request id; `path` is accepted for script compatibility but ignored by this binding. |
| `url_encode` | `http.url_encode(s: string) -> string` | safe | Percent-encodes `s` for use in URLs. |
| `escape_html` | `http.escape_html(s: string) -> string` | safe | Returns `s` with `&`, `<`, `>`, `"`, `'` replaced by their HTML entity equivalents. |
| `get_async` | `http.get_async(url: string, cb: function?, headers: table?) -> integer` | safe | Fires a GET request and returns the request id; the optional callback is invoked with the response, and headers (if given) are read from arg 3. |
| `in_flight` | `http.in_flight() -> integer` | safe | Returns the number of HTTP requests currently in flight across the client. |
| `max_body_size` | `http.max_body_size() -> integer` | safe | Returns the maximum response body size, in bytes, that the HTTP client will accept. |
| `max_concurrent` | `http.max_concurrent() -> integer` | safe | Returns the current cap on simultaneous in-flight HTTP requests. |
| `max_timeout_ms` | `http.max_timeout_ms() -> integer` | safe | Returns the maximum per-request timeout the HTTP client will honour, in milliseconds. |
| `metrics` | `http.metrics() -> table` | safe | Returns a snapshot of HTTP counters: {sent, ok, failed, in_flight, bytes_up, bytes_down}. |
| `parse_url` | `http.parse_url(url: string) -> table` | safe | Parses url into a table with scheme, host, path, query (strings) and port (integer); missing components come back as empty strings or 0. |
| `post_async` | `http.post_async(url: string, body: string, cb: function\|nil, headers: table\|nil) -> integer` | safe | Submits an async POST and returns the request id; `cb` receives the response, and the optional headers table is read from arg 4. |

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
| `on_connect` | `net_channel.on_connect(...: any) -> nil,string` | safe | Not-implemented stub: returns `nil, "not implemented; no client connect hook wired"`. |
| `on_disconnect` | `net_channel.on_disconnect(...: any) -> nil,string` | safe | Not-implemented stub inherited from the `network` table; returns `nil` plus the reason string (no client disconnect hook is wired). |
| `bandwidth_bytes_per_sec` | `net_channel.bandwidth_bytes_per_sec() -> number` | safe | Returns the sum of average inbound and outbound bytes per second on the local net channel. |
| `on_message` | `net_channel.on_message(...: any) -> nil,string` | safe | Not-implemented stub; returns nil plus the message "not implemented; use net.on_message for game user_messages". |
| `clear_handlers` | `net_channel.clear_handlers() -> boolean` | safe | Alias of `network.clear_handlers`: returns true for trusted callers and false otherwise. |
| `ping` | `net_channel.ping() -> integer` | safe | Alias of `network.ping`: returns current local latency in milliseconds. |
| `connect_to_server` | `net_channel.connect_to_server(...): (nil, string: any)` | safe | Not implemented: client-side connect is not wired. Returns nil and the reason string. |
| `send_bytes` | `net_channel.send_bytes(...): (nil, string: any)` | safe | Not implemented: raw packet send is not wired. Returns nil and the reason string. |
| `connected` | `net_channel.connected() -> boolean` | safe | Alias of network.connected: returns whether the client is in-game. |
| `send_json` | `net_channel.send_json(...: any) -> nil, string` | safe | Not-implemented stub inherited from the network table; returns nil and the string "not implemented". |
| `disconnect` | `net_channel.disconnect(...: any) -> nil` | safe | Not implemented — returns nil plus the reason string. |
| `send_reliable` | `net_channel.send_reliable(...: any) -> nil` | safe | Not implemented — returns nil plus the reason string. |
| `flush_send` | `net_channel.flush_send(...: any) -> nil, string` | safe | Not implemented; always returns `nil, "not implemented"`. |
| `send_string` | `net_channel.send_string(...: any) -> nil, string` | safe | Not implemented; always returns `nil, "not implemented"`. |
| `get_server_ip` | `net_channel.get_server_ip() -> nil,string` | safe | Inherited from `network.get_server_ip`; always returns nil and the string "not implemented". |
| `send_unreliable` | `net_channel.send_unreliable(...: any) -> nil,string` | safe | Not implemented: returns nil and the refusal reason "not implemented". |
| `get_server_port` | `net_channel.get_server_port() -> nil, string` | safe | Not implemented: returns nil plus the string `"not implemented"`. |
| `stats` | `net_channel.stats() -> table` | safe | Snapshot of the local net channel: `ping`, `loss`, `choke`, `latency_ms`, `latency`, `packets_in`, `packets_out`, `bytes_in`, `bytes_out`, `uptime_seconds`, `connected`. |
| `handler_counts` | `net_channel.handler_counts() -> table` | safe | Returns a table of per-event handler counts; currently reports zeros for on_connect, on_disconnect, and on_message since those hooks are not wired. |
| `uptime_seconds` | `net_channel.uptime_seconds() -> integer` | safe | Returns the engine's current real-time in whole seconds, or 0 when global vars are unavailable. |
| `is_connected` | `net_channel.is_connected() -> boolean` | safe | Returns whether the client is in a game (copied from `network.is_connected`). |
| `last_error` | `net_channel.last_error() -> string` | safe | Stub that always returns an empty string; copied in from `network.last_error`. |
| `latency_ms` | `net_channel.latency_ms() -> integer` | safe | Returns the outgoing-flow round-trip latency in milliseconds (seconds *1000, rounded). |
| `loss` | `net_channel.loss() -> number` | safe | Alias of `network.loss`: returns `Avalanche::Core::Net::GetLocalPacketLoss(1)` (the local client's packet-loss fraction on net channel 1). |
| `max_packet_size` | `net_channel.max_packet_size() -> integer` | safe | Returns the fixed packet-size cap of 1200 bytes (inherited from `network.max_packet_size`). |

### net

`namespace` · tier `safe` — Generic inbound protobuf message read (reflection-based).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_message` | `net.on_message(name_or_id: string\|integer, callback: fun(msg:table)) -> integer` | safe | Register an observer for inbound user-messages. matcher = descriptor name/full_name, a numeric msg id, or "*" for all. callback(msg) receives the decoded protobuf fields as a table (+ .name / .id); its return value is IGNORED (never swallows the message). A handler registered from inside a coroutine keeps firing after the coroutine is collected. Returns a handle. |
| `remove_message` | `net.remove_message(handle: integer) -> boolean` | safe | Remove a handler registered via net.on_message (true if found). |

### proto

`namespace` · tier `safe` — Bidirectional protobuf: parse raw bytes into a table, or serialize a table into bytes, by message type name.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `parse` | `proto.parse(type_name: string, bytes: string) -> table\|nil` | safe | Decode raw wire bytes of message `type_name` into a Lua table of its fields via reflection (nested messages depth-capped, repeated -> 1-based arrays). Returns nil + logs on unknown type / parse failure. |
| `serialize` | `proto.serialize(type_name: string, tbl: table) -> string\|nil` | safe | Build a fresh `type_name` message from `tbl` via reflection setters, then serialize to raw bytes (a Lua string). Unknown keys / type mismatches are logged + skipped; returns nil + logs on unknown type / serialize failure. |
| `has_type` | `proto.has_type(type_name: string) -> boolean` | safe | True if `type_name` is a message type known to the generated descriptor pool. |
| `list_types` | `proto.list_types() -> table` | safe | Array of known message full-names (dependency closure of the core network message files; deduped, sorted, capped) for discoverability. |
| `from_json` | `proto.from_json(type_name: string, json: string) -> table\|nil,string?` | safe | Alias of `protobuf.from_json`. |
| `get_field` | `proto.get_field(type_name: string, msg: table, field_name: string) -> any\|nil` | safe | Alias of `protobuf.get_field`. Materializes `msg` as an instance of the named descriptor and pushes the named field's value; nil when the runtime is not ready, arguments are empty, or the field/type is unknown. |
| `message` | `proto.message(type_name: string) -> table\|nil` | safe | Alias of `protobuf.new`: looks up `type_name` in the protobuf runtime and returns a fresh empty message table, or nil when the type is unknown. |
| `new` | `proto.new(type_name: string) -> table\|nil` | safe | Alias of `protobuf.new`. |
| `set_field` | `proto.set_field(type_name: string, tbl: table, field_name: string, value: any) -> boolean` | safe | Alias of `protobuf.set_field`. |
| `to_json` | `proto.to_json(type_name: string, source: any, pretty: boolean\|nil) -> string\|nil, string` | safe | Alias of protobuf.to_json. |
| `available` | `proto.available() -> boolean` | safe | Alias of `protobuf.available`. |
| `validate` | `proto.validate(...: any) -> boolean` | safe | Alias of `protobuf.validate` — currently a stub that always returns true. |
| `clone` | `proto.clone(msg: table) -> table` | safe | Alias of `protobuf.clone`. |
| `version` | `proto.version() -> string` | safe | Alias of `protobuf.version`. |
| `decode` | `proto.decode(type_name: string, bytes: string) -> table\|nil,string` | safe | Alias of `protobuf.parse`: decodes bytes of the named message type into a Lua table, or returns nil and an error string. |
| `describe` | `proto.describe(type_name: string) -> table\|nil` | safe | Alias of `protobuf.describe`. |
| `encode` | `proto.encode(type_name: string, msg: table) -> string\|nil, string?` | safe | Alias of `protobuf.serialize`: builds a message of the given type from the table and returns its wire bytes, or nil plus an error string on failure. |
| `enumerate_fields` | `proto.enumerate_fields(type_name: string) -> table` | safe | Alias of `protobuf.field_names`. |
| `enumerate_messages` | `proto.enumerate_messages() -> table` | safe | Alias of `protobuf.list_types`; returns an array of fully qualified message type names registered in the generated descriptor pool. |
| `field_names` | `proto.field_names(type: string) -> table` | safe | Alias of `protobuf.field_names`. |
| `field_types` | `proto.field_types(type_name: string) -> table` | safe | Alias of `protobuf.field_types`: returns a table keyed by field name whose values are the protobuf CppType integer for each field of the named message; empty when the descriptor runtime is unavailable or the type is unknown. |
| `find_message` | `proto.find_message(type_name: string) -> string\|nil` | safe | Looks up a message type by name and returns the descriptor's full name; nil if the runtime is not ready or the type is unknown. |

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
| `ease_in` | `anim.ease_in(t: number) -> number` | safe | Cubic ease-in on t∈[0,1] (t*t*t). |
| `ease_out` | `anim.ease_out(t: number) -> number` | safe | Cubic ease-out on t∈[0,1]. |
| `ease_in_out` | `anim.ease_in_out(t: number) -> number` | safe | Cubic ease-in-out on t∈[0,1]. |
| `smoothstep` | `anim.smoothstep(t: number) -> number` | safe | Smoothstep curve on t∈[0,1] (3t²−2t³). |
| `lerp` | `anim.lerp(a: number, b: number, t: number) -> number` | safe | Scalar linear interpolation, a + (b-a)*t (not clamped). |
| `lerp_angle` | `anim.lerp_angle(a: number, b: number, t: number) -> number` | safe | Interpolates between two angles (degrees) along the shortest arc. |
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
| `green` | `color.green() -> Color` | safe | Returns the preset green `Color`. |
| `red` | `color.red() -> Color` | safe | Returns the canonical red Color via `Color::red()`. |
| `rgba` | `color.rgba(r: integer, g: integer, b: integer, a: integer) -> Color` | safe | Constructs a Color from four 0-255 channel values; each component is clamped to the byte range. |
| `white` | `color.white() -> Color` | safe | Returns the opaque white Color. |
| `with_alpha` | `color.with_alpha(c: Color, a: integer) -> Color` | safe | Returns a copy of c with its alpha replaced by a. |
| `yellow` | `color.yellow() -> Color` | safe | Returns the canonical yellow color. |
| `black` | `color.black() -> Color` | safe | Returns the opaque black Color constant. |
| `blue` | `color.blue() -> Color` | safe | Returns the preset blue color (Color::blue()). |
| `clear` | `color.clear() -> Color` | safe | Fully transparent black (0,0,0,0). |

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
| `clear_all` | `esp.clear_all() -> nil` | safe | Clears every ESP element registered by scripts and notifies listeners that the ESP set has changed. |
| `count` | `esp.count() -> integer` | safe | Returns the current number of registered ESP elements. |
| `query` | `esp.query(entity_index: integer) -> table\|nil` | safe | Looks up this frame's ESP target buffer for that entity index and returns a table with entity, on_screen and, when the entity was captured, is_enemy, visible and box_left/top/right/bottom; returns nil when the arg is not a positive integer. |
| `register_element` | `esp.register_element(name: string, fn: fun(...):any) -> integer\|nil` | safe | Registers a Lua ESP contributor identified by `name` to be called each frame; returns the registry id to pass back to `esp.unregister_element`, or nil on bad args/allocation failure. |
| `unregister_element` | `esp.unregister_element(id: integer)` | safe | Removes the previously registered ESP contributor with the given registry id and frees its holder. |

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
| `current_hero` | `HeroCfg.current_hero() -> table\|nil` | safe | Returns `{id = <EHeroID>, name = <codename>}` for the local hero, or nil when no local hero is resolvable. |
| `list_heroes` | `HeroCfg.list_heroes() -> table` | safe | Returns an array of {id, name} tables for every hero in the current HeroScriptStore snapshot; empty when no snapshot is available. |
| `manual_enabled` | `HeroCfg.manual_enabled(slot: integer) -> boolean` | safe | Returns whether manual combo play is enabled for that ability slot (slot resolved from the first argument; false when the slot is invalid). |
| `session_open` | `HeroCfg.session_open(slot: integer\|nil) -> boolean` | safe | Returns true when the manual combo session latch is open for `slot` (invalid slot returns false). |

### ComboOpt

`namespace` · tier `safe` — Declare your own option rows on the native Heroes page (per ability / per combo item / per always-on FEATURE) and read them back. Owner + hero are auto-filled.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ability` | `ComboOpt.ability(slot: integer, hero?: integer) -> ComboOptScope` | safe | A declaration scope on signature ability `slot` (0..3) of the LOCAL hero — the rows appear in that ability's Aim & Targeting child. Pass `hero` to target a specific hero id, or 0 to show the rows on EVERY hero. |
| `item` | `ComboOpt.item(item: integer\|string, hero?: integer) -> ComboOptScope` | safe | A declaration scope on a combo ITEM — its EComboItem ordinal or its "upgrade_*" vdata token ("upgrade_metal_skin"). The rows appear in that item's combo card. Pass `hero` to target a specific hero id, or 0 for every hero. |
| `get` | `ComboOpt.get(key: string) -> any` | safe | The live value of one of THIS script's declared options (nil if it never declared `key`). Bool -> boolean, slider -> number, slider_int -> integer, enum -> the 1-based index into `choices`. Cheap enough to call every tick (cached handle + atomic read, no menu lock). ComboOpt.get(owner, key) reads another script's option. |
| `feature` | `ComboOpt.feature(spec: table)` | safe | Declare an always-on FEATURE: an enabled toggle (+ optional bind) plus 0..N sub-option rows. spec = { key, label, blurb?, default?, bind?, hero?, slot?, options={ { type="toggle"\|"slider"\|"slider_int"\|"dropdown"\|"color"\|"header"\|"hint", key, label?, tooltip?, default?, min?, max?, step?, fmt?, choices?, bind?, depends_on?, depends_value?, depends_not? }, ... } }. Read back with feature.enabled / feature.value. A bare `slider` with an integer `step` rounds (Int); otherwise it is a Float. `depends_on` names a sibling option key; `depends_not=true` inverts the depends_value test (show when the sibling != depends_value). Optional `slot` (0..3) binds the feature to an ability so the per-ability panel cross-links to it. Option type "multi" takes choices (at most 24) and a default list / set / mask. `depends = { { on, value, negate }, ... }` lists more conditions, all of which must hold. Feature flags: casts (the feature fires its slot's ability; its helper row reads "Auto: <Ability>"), indicator (a slotless read-out the hero page seats on its Kill Indicator row). |
| `dirty` | `ComboOpt.dirty() -> boolean` | safe | Returns true if the combo-option registry has pending unsaved changes. |
| `exists` | `ComboOpt.exists(name: string) -> boolean` | safe | Returns true when a combo option named `name` is registered. |
| `kind_of` | `ComboOpt.kind_of(path: string) -> string\|nil` | safe | Returns the kind name of the combo option at `path` (bool, int, float, enum, color, multi, …), or nil if no such row exists. |
| `mark_saved` | `ComboOpt.mark_saved()` | safe | Marks the combo-option registry as saved (clears the dirty flag). |
| `register` | `ComboOpt.register(desc: table) -> integer` | safe | Registers a combo option row from a descriptor table (slot/item/hero_id/kind/feature/bindable, plus kind-specific fields) and returns the row id; 0 if the arg is not a table or the row fails to build. |
| `remove_owned` | `ComboOpt.remove_owned() -> nil` | safe | Removes every ComboOpt row registered by the calling script's namespace. |
| `set` | `ComboOpt.set(key: string, value: any) -> boolean` | safe | Writes `value` into the combo-option row identified by `key`, converting per the row's kind (bool/int/float/color/enum uses 1-based index/multi-select mask), then clamps and returns true; false if `key` is not a string or the row is missing. |

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
| `find_path` | `Panorama.find_path(ids: table) -> PanoramaPanel\|nil` | safe | Resolves a list of panel ids relative to the Panorama root and returns the matching panel handle, or nil when no panel replies. |

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
| `set_attribute` | `:set_attribute(name: string, value: string) -> PanoramaPanel` | safe | Calls `panel.SetAttributeString(name, value)` on the panorama panel via a dispatched script. Gated behind the `panorama` capability; a no-op without it. Returns self. |
| `run_script` | `:run_script(js: string) -> PanoramaPanel` | safe | Run JS with local self bound to this panel. |
| `remove` | `:remove() -> PanoramaPanel` | safe | DeleteAsync(0) (deferred destroy). |
| `delete` | `:delete() -> PanoramaPanel` | safe | Alias of remove. |
| `id` | `:id() -> string` | safe | The id this handle was built from (no readback). |
| `valid` | `:valid() -> boolean` | safe | STRUCTURAL validity only (selector non-empty); NOT a live-existence check. |
| `has_selector` | `:has_selector() -> boolean` | safe | Same STRUCTURAL check as valid() under an honest name (selector non-empty); NOT a live-existence check. |
| `get_attribute` | `:get_attribute(name: string) -> nil` | safe | Not implemented: raises an error (the Panorama bridge has no JS-to-Lua return channel). |
| `children` | `:children() -> table` | safe | Not implemented: raises an error (the Panorama bridge has no JS-to-Lua return channel). |
| `exists` | `:exists() -> boolean` | safe | True when the Panorama selector currently resolves to a live panel. |
| `find_child_by_path` | `:find_child_by_path(ids: table) -> PanoramaPanel\|nil` | safe | Walks the array of child ids under self and pushes the resolved panel, or nil when the path cannot be verified. |
| `find_child_with_class` | `:find_child_with_class(class_name: string) -> PanoramaPanel\|nil` | safe | BFS-walks up to 4000 descendants of this panel in the Panorama JS context looking for one with the given CSS class and returns the first match as a PanoramaPanel, or nil when no reply or no match. |
| `find_children_traverse` | `:find_children_traverse(id: string) -> table` | safe | Walks the panel's descendants (BFS, 4000-node cap) and returns a list of panels whose `id` matches. |
| `get_bounds` | `:get_bounds() -> number, number, number, number` | safe | Queries the panel's window-space `x`, `y`, actual-layout width, and actual-layout height as four return values; pushes a single nil if the Panorama query fails. |
| `get_child` | `:get_child(index: integer) -> PanoramaPanel\|nil` | safe | Asks the panel for its i-th child via Panorama JS; returns a new PanoramaPanel bound to the child selector, or nil for negative indices and misses. |
| `get_child_count` | `:get_child_count() -> integer\|nil` | safe | Queries the Panorama panel for `GetChildCount()`; returns the integer count, or nil when the panel query fails. |
| `has_class` | `:has_class(class_name: string) -> boolean\|nil` | safe | Queries the panel in Panorama for `BHasClass(class_name)`; returns the boolean result, or nil if the panel query fails. |

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
| `call_convention` | `native.call_convention(...: any) -> nil,string` | safe | Refusal stub: returns `nil, reason` — calling-convention selection is disabled by policy. |
| `syscall_by_hash` | `native.syscall_by_hash(...: any) -> nil,string` | safe | Refusal stub: returns `nil, reason` — raw NT syscalls by name-hash are disabled by policy. |
| `enumerate_exports` | `native.enumerate_exports() -> table` | safe | Returns an empty table; native export enumeration is not exposed to Lua. |
| `syscall_by_ordinal` | `native.syscall_by_ordinal(...: any) -> nil` | safe | Policy refusal: raw NT syscalls by ordinal are disabled; raises a Lua error. |
| `get_export` | `native.get_export(...: any) -> any` | safe | Refusal stub: DLL export lookup from Lua is disabled by policy. |
| `thread_hijack` | `native.thread_hijack(...: any) -> any` | safe | Refusal stub: thread hijack from Lua is disabled by policy. |
| `get_export_by_hash` | `native.get_export_by_hash(...: any) -> any` | safe | Refusal stub: hashed DLL export lookup from Lua is disabled by policy. |
| `get_return` | `native.get_return(...): (nil, string: any)` | safe | Refusal stub: native return-value fetch is disabled because there is no invocation surface to feed. Returns nil and the refusal reason. |
| `invoke` | `native.invoke(...: any) -> nil` | safe | Refusal binding: errors with "native.invoke: arbitrary function invocation is disabled by policy." |
| `invoke_cdecl` | `native.invoke_cdecl(...: any) -> nil` | safe | Disabled by policy — always returns nil, and (when the `native` capability is granted to see refusals) the reason string as the second value. |
| `invoke_fastcall` | `native.invoke_fastcall(...: any) -> nil` | safe | Policy refusal: arbitrary `__fastcall` invocation from Lua is disabled; calling raises a Lua error with the reason. |
| `invoke_stdcall` | `native.invoke_stdcall(...: any) -> nil,string` | safe | Disabled by policy: pushes nil and the refusal reason "native.invoke_stdcall: __stdcall invocation is disabled by policy." |
| `invoke_thiscall` | `native.invoke_thiscall(...: any) -> nil` | safe | Disabled by policy: errors with a refusal message explaining that `__thiscall` invocation from Lua is not permitted. |
| `list_interfaces` | `native.list_interfaces() -> table` | safe | Returns an empty table; raw engine interface enumeration from Lua is disabled by policy. |
| `resolve_interface` | `native.resolve_interface(...: any) -> nil, string` | safe | Refusal stub: engine `CreateInterface` resolution from Lua is disabled by policy; returns nil and the refusal message. |
| `resolve_symbol` | `native.resolve_symbol(...: any) -> nil,string` | safe | Refusal stub: returns nil plus a reason saying exported-symbol resolution from Lua is disabled by policy. |
| `set_arg` | `native.set_arg(...: any) -> nil,string?` | safe | Policy refusal; argument stashing is disabled because there is no exposed invocation surface. Returns nil (and a reason once the native capability is granted). |
| `apc_queue` | `native.apc_queue(...: any) -> nil,string` | safe | Policy refusal: always returns nil and the message "native.apc_queue: APC queue injection from Lua is disabled by policy." |
| `set_calling_convention` | `native.set_calling_convention(...: any) -> nil,string` | safe | Policy refusal: always returns nil and the message "native.set_calling_convention: calling convention override is disabled by policy." |
| `call` | `native.call(...: any) -> any` | safe | Refusal stub: errors with "native.call: arbitrary function invocation is disabled by policy. Use vetted subsystem APIs." |
| `syscall` | `native.syscall(...: any) -> any` | safe | Refusal stub: errors with "native.syscall: raw NT syscall is disabled by policy." |

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

_No members._

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
| `is_lp_valid` | `HERO_LIB.is_lp_valid() -> boolean` | safe | True when the local player pawn pointer is non-null in the entity frame. |
| `is_lp_alive` | `HERO_LIB.is_lp_alive() -> boolean` | safe | True when the local-player frame record is valid and the pawn is marked alive. |
| `get_health` | `HERO_LIB.get_health() -> integer` | safe | Returns the local pawn's current health (from frame Facts); 0 when the local pawn is missing. |
| `get_health_percent` | `HERO_LIB.get_health_percent() -> number` | safe | Returns the local pawn's health as a fraction of its maximum (0..1). |
| `units_to_meters` | `HERO_LIB.units_to_meters(units: number) -> number` | safe | Converts a Source-engine distance in units to meters via Math::UnitsToMeters. |
| `game_time` | `HERO_LIB.game_time() -> number` | safe | Returns the current game time in seconds (av::combo::get_game_time). |
| `is_ability_ready` | `HERO_LIB.is_ability_ready(ability: Ability\|integer, count_cast_delay?: boolean, accepted_codes?: table) -> boolean, boolean` | safe | Validated readiness: ready, casting. ability is an Ability, the light userdata HERO_LIB.get_ability returns, or a slot number. On the game thread inside the tick it asks the game (the action record's answer for an ability an action presses, one memoised activation check per ability per tick otherwise): Success is ready, PositionInvalid and CantCastPassive count as ready off cooldown, and so does any code in accepted_codes (each an ECitadelAbilityOrders name or number). Elsewhere the hand rules answer. count_cast_delay = true also accepts an ability inside its own cast delay, and then the second result `casting` is true. CHANGED: second result and accepted_codes are new; the game's answer is used on the game thread. |
| `is_ability_in_cd` | `HERO_LIB.is_ability_in_cd(ability: Ability\|integer, force_chargeable?: boolean) -> boolean` | safe | Cooling down, or no charge left on a chargeable ability. Accepts an Ability, light userdata or a slot number. force_chargeable: nil lets the ability's AbilityCharges decide, true treats it as chargeable, false as not. |
| `is_ability_in_cast_delay` | `HERO_LIB.is_ability_in_cast_delay(ability: Ability\|integer, no_start_offset?: boolean, delay?: number, start?: number) -> boolean` | safe | TIME-WINDOW test (NOT the m_bInCastDelay bool), Umbrella's window: start <= now + 1 s and now <= start + delay, so a start stamp up to 1 s ahead of the clock (the client's predicted press) counts. no_start_offset = true drops that 1 s lead. Optional delay / start override AbilityCastDelay and m_flCastDelayStartTime, so a caller that already read the pair skips the property resolve. False for a null ability, one authoring no cast delay, one never cast. For the raw schema flag use ability_in_cast_delay. CHANGED: arg 2 was an unread filler and the window had no lead. |
| `is_ability_in_self_cast_delay` | `HERO_LIB.is_ability_in_self_cast_delay(ability: Ability\|integer) -> boolean` | safe | The local hero's alternate-cast (self-cast) window is open for the ability: game time < the alt-cast hold start + cl_citadel_ability_alt_cast_hold_time, or the double-tap start + the double-tap timeout, by the player's alt-cast mode; false in the modifier-key mode. CHANGED: it was an alias of is_ability_in_cast_delay (same signature). |
| `get_scaled_property` | `HERO_LIB.get_scaled_property(ability: Ability, key: string) -> number` | safe | Caster-scaled property value (spirit power, item bonuses). Game thread only; an off-thread call returns the authored base value. Range and length keys come back in UNITS. Same as Ability:get_scaled_property. |
| `dump_ability` | `HERO_LIB.dump_ability(ability: Ability)` | safe | GROUND-TRUTH AUDIT AID. Appends this ability/item class's REAL authored property set (every VData-enumerated key + its scaled value) to C:\Avalanche\Config\ability_properties_dump.txt, one section per class. Deduped by class name in C++, so repeat/per-tick calls are a cheap early return (no per-tick I/O). Game-thread only. Use to discover exact property names for readers. |
| `get_cast_range` | `HERO_LIB.get_cast_range(ability: Ability) -> number` | safe | Scaled cast range in UNITS, including cast-range items (Greater Expansion etc.); 4000 when the ability declares none. Same producer as Ability:get_cast_range and get_ability_range. |
| `get_cast_delay_fraction` | `HERO_LIB.get_cast_delay_fraction(ability: Ability) -> number` | safe | Cast-delay progress in [0, 1] from the cast start time and the AbilityCastDelay property. CHANGED: 0 (was 1) outside the cast delay and for an ability with no cast delay. |
| `has_ability` | `HERO_LIB.has_ability(name: string) -> boolean` | safe | True if the local hero owns an ability whose class matches `name` (AbilityComponent class-name scan). |
| `is_on_ground` | `HERO_LIB.is_on_ground(pawn?: PlayerPawn) -> boolean` | safe | True when the given pawn (or the local pawn if omitted) has the FL_ONGROUND entity flag set. |
| `get_stamina` | `HERO_LIB.get_stamina() -> number\|nil` | safe | The local hero's stamina pool now (the dash / air-move charges); nil without a local hero. |
| `max_stamina` | `HERO_LIB.max_stamina() -> number\|nil` | safe | The local hero's stamina pool size; nil without a local hero. |
| `get_dash_jump_state` | `HERO_LIB.get_dash_jump_state(pawn: PlayerPawn) -> table\|nil` | safe | Engine dash-jump window { can_dash_jump, window_start, window_end, consecutive_air_dashes, ok }. Same read the INNATE.DASH_JUMP precondition uses. Reads the same action record as native automation. nil, not 0, when there is no state (0 is truthy in Lua). For the local hero the table also carries run_time (the game time the next command runs at) and now (true when a jump in that command is the game's dash-jump: ground dash, window and stamina, the jump ability's rule). |
| `INNATE` | `.INNATE: table` | safe | Innate action ids: LIGHT_MELEE, HEAVY_MELEE, PARRY, SLIDE, JUMP, MANTLE, ZIPLINE, DASH_JUMP. |
| `innate_count` | `.innate_count: integer` | safe | Number of innate actions. |
| `innate_ready` | `HERO_LIB.innate_ready(action: integer) -> boolean` | safe | Can this innate fire right now? (parry off cooldown, dash jump inside its window, slide grounded+moving, melee not mid-swing...) |
| `innate_press` | `HERO_LIB.innate_press(cmd: UserCmd, action: integer) -> boolean` | safe | Perform the innate on this tick's command. Presses the real input bit and arms its hold. false = the precondition failed and nothing was pressed. |
| `innate_holding` | `HERO_LIB.innate_holding(action: integer) -> boolean` | safe | True while the innate's hold is still running (heavy melee still charging). Wait on this before advancing a combo step. |
| `innate_release_all` | `HERO_LIB.innate_release_all()` | safe | Drop every innate hold (combo aborted). |
| `innate_info` | `HERO_LIB.innate_info(action: integer) -> table\|nil` | safe | { name, bits, charged, hold_seconds, delegated } for an innate action. |
| `innate_for_melee_kind` | `HERO_LIB.innate_for_melee_kind(melee_kind: integer) -> integer` | safe | Randomized-melee step kind (1 = light, 2 = heavy) -> the innate action index. -1 = not a melee step. |
| `lp_hero_id` | `HERO_LIB.lp_hero_id() -> integer` | safe | Returns the local player's hero id, or -1 when the local controller is not yet available. |
| `is_channeling_ability` | `HERO_LIB.is_channeling_ability(ability: Ability) -> boolean` | safe | True when av::combo::is_ability_channeling reports the given ability (or slot) as currently channeling. |
| `get_target_pos` | `HERO_LIB.get_target_pos(target: PlayerPawn, lead?: boolean) -> Vector3\|nil` | safe | The target's body point, led two ticks on its networked velocity (lead = false returns the point itself). The point follows Umbrella's bone order: the root while burrowed, the spine of a hex / cat / Baba rig, else the mid-torso aim centre. nil when the frame holds no row for the pawn. |
| `predict_target` | `HERO_LIB.predict_target(target: PlayerPawn, lead?: boolean) -> Vector3\|nil` | safe | Same function as get_target_pos. |
| `get_origin` | `HERO_LIB.get_origin(pawn: PlayerPawn) -> Vector3` | safe | The same value as pawn:get_origin(): the per-tick origin on the game thread, the live interpolated origin off it. nil for an invalid pawn. CHANGED: used to be a live read that could differ from pawn:get_origin() inside the same callback. |
| `get_velocity` | `HERO_LIB.get_velocity(pawn?: PlayerPawn) -> Vector3` | safe | Velocity (units/s) from this tick's EntityFrame (once per tick) of the pawn, default the local pawn; (0, 0, 0) when the frame does not hold it. |
| `get_heroes_in_radius` | `HERO_LIB.get_heroes_in_radius(pos: Vector3, radius: number, opts?: table) -> PlayerPawn[]` | safe | radius is in game UNITS, NOT meters (convert a meters value with HERO_LIB.METERS_TO_UNITS first). Without opts: every hero pawn the frame holds within radius of pos. With opts { allies, enemies, visible_only, active_only, predict_s, include_local }: living, non-dormant heroes other than the local one (unless include_local); allies / enemies pick the sides (both when neither is named); visible_only keeps those seen from the local eye; active_only drops is_inactive_target pawns; predict_s measures each hero where simulate_movement_for_duration puts it after that many seconds. |
| `entities_by_class` | `HERO_LIB.entities_by_class(class_slug: string, opts?: table) -> table[]\|nil` | safe | By-CLASS entity query over the per-tick entity frame — the ONLY path to a non-pawn entity (turret / trap / soul / breakable / projectile). `class_slug` is an entity-class slug (the value the Heroes page's "Entity class" target dropdown stores). Rows are NEAREST FIRST: { pos (the class's declared aim point), origin, dist (units), handle, team, enemy, mine (the local pawn threw/owns it), visible (only when opts.require_visible), class, pawn (the `players` class only) }. opts = { origin:Vector3, max_range_u, team="enemy"\|"ally"\|"any", mine, require_visible, limit }. Returns NIL (not an empty table) when the slug is not a known class, so a bad config reports itself. |
| `should_ignore_target` | `HERO_LIB.should_ignore_target(pawn: PlayerPawn) -> boolean` | safe | Does the user's IGNORE list reject this pawn? The same ScriptHelpers::ShouldIgnoreTarget filter find_combo_target applies to every candidate. Any pick made OUTSIDE find_combo_target (a radius scan, a fallback) must ask this or it can return a hero the user told the aimbot to ignore. An invalid pawn ignores (fail-closed). |
| `get_fov_to_pos` | `HERO_LIB.get_fov_to_pos(pos: Vector3, opts?: table) -> number` | safe | Degrees between the view and the point; 180 before the first local capture. Every aim cone is a radius in this unit. Optional opts { from, angles, only_yaw } replace the camera position, the view angles and the pitch rule (only_yaw: both pitches count as 0). 180 also when a default the options do not replace is missing. |
| `is_pos_within_fov` | `HERO_LIB.is_pos_within_fov(pos: Vector3, fov: number, opts?: table) -> boolean` | safe | true when the point is at most `fov` degrees from the view (a cone radius, default 45), the gate every aim cone uses. opts as get_fov_to_pos. |
| `no_obs_to_pos` | `HERO_LIB.no_obs_to_pos(from: Vector3, to: Vector3, target?: Entity, allowed?: number) -> boolean` | safe | is_line_free from `from` to `to`: an enemy body in the line blocks it, `target` (any entity) counts as clear, teammates and the local hero do not count; free when the fraction reaches `allowed` (1). Off the game thread the published visibility answers. CHANGED: an engine trace on the game thread. |
| `no_obs_to_target` | `HERO_LIB.no_obs_to_target(target: PlayerPawn, from?: Vector3, allowed?: number) -> boolean` | safe | The line from `from` (the camera by default) to the pawn's body point, as no_obs_to_pos with the pawn as target. |
| `get_hitbox_aim` | `HERO_LIB.get_hitbox_aim(target: PlayerPawn, hitbox_bits: integer) -> Vector3\|nil` | safe | Resolve a Hitbox-widget bitfield (bits 0-4 enabled Head/Neck/Torso/Arms/Legs, bits 5-9 priority) to the picked bone's world position. nil = bones not resolvable this frame. Needs the target in the aim set: nil for one tick at first sight, and always for allies and the local pawn. |
| `resolve_aim_point` | `HERO_LIB.resolve_aim_point(target: PlayerPawn, opts: table) -> Vector3\|nil` | safe | The Heroes-page "Point mode" aim point, all five modes: opts = { mode = 0 Hitboxes \| 1 Bone \| 2 Height offset \| 3 Closest surface \| 4 Origin, bits (the hitbox bitfield, modes 0/3), bone (a model bone NAME, mode 1), z (units, mode 2) }. Mode 3 returns the point on the picked hitbox's SURFACE nearest the cast ray — the aim point that minimises the PSilent camera-position offset. nil = unresolvable; the caller keeps its own fallback. Hitbox modes (0, 3) need the target in the aim set: nil for one tick at first sight, and always for allies and the local pawn. |
| `predict_projectile` | `HERO_LIB.predict_projectile(check_obstruction: boolean, info_from: integer, sim_tier: integer, aim_to_pos: integer, target: PlayerPawn, ability: Ability, caster?: PlayerPawn, opts?: table) -> (Vector3\|nil, Vector3, table, table, number, boolean)` | safe | Projectile lead solver. ARG ORDER IS EXACT: check_obstruction (ignored), info_from = ENUM_PPS_INFO_FROM (0 PROJECTILE / 1 GUN), sim_tier = ENUM_MV_SIM_TYPE, aim_to_pos = ENUM_PPS_AIM_TO_POS, then target, ability, optional caster (defaults to local pawn). Trailing opts = { speed=, radius=, hitbox= } — the hitbox bitfield goes HERE, NOT positionally. Returns aim_pos, sim_pos, traj, path, lead_time, blocked. aim_pos is nil when there is no solution. lead_time (5th) = PHYSICAL flight-time lead in SECONDS, NO ping term (native prediction is latency-blind by design; add net_channel.latency yourself for total lead). blocked (6th) = TRUE when the shot was VETOED: its trajectory (swept with the ability's real radius, arc-aware) would hit world geometry before reaching the target, or the target won't be hittable at the predicted impact (rounded a corner). blocked=true means DO NOT CAST (hold/skip); a plain nil aim_pos with blocked=false is a benign miss (fall back to a static point). The target velocity is the frame's smoothed (EMA) velocity, updated once per tick. With hitbox bits the target must be in the aim set: nil for one tick at first sight, and always for allies and the local pawn. sim_tier and aim_to_pos are accepted and ignored. With a solution the results are (aim, aim, {}, {aim}, lead, false); without one (nil, nil, {}, {}, 0, blocked). |
| `predict_projectile_simulated` | `HERO_LIB.predict_projectile_simulated(check_obstruction: boolean, info_from: integer, sim_tier: integer, aim_to_pos: integer, target: PlayerPawn, ability: Ability, caster?: PlayerPawn, opts?: table) -> (Vector3\|nil, Vector3, table, table, number, boolean)` | safe | ALIAS of predict_projectile — the SAME function pointer (&PredictProjectileImpl), not a separate simulated solver. Same exact 8-arg signature (hitbox goes in the trailing opts table, not positionally). 5th return lead_time = flight-time lead in SECONDS, no ping term. 6th return blocked = the collision/visibility VETO (true = trajectory hits world geometry / target not hittable at impact = DO NOT CAST). Same velocity and aim-set notes as predict_projectile. |
| `bullet_gravity` | `HERO_LIB.bullet_gravity() -> number` | safe | The local weapon's bullet drop in units/s^2 (m_flBulletGravityScale x sv_gravity, 800 on standard servers; 0 without a local controller). The BASE scale, without a gravity-by-distance curve (Rat King); prediction.gravity(nil, distance) gives the effective value for a shot that long. weapon_stats().gravity is the same value. |
| `hull_projectile_will_hit` | `HERO_LIB.hull_projectile_will_hit(from: Vector3, pos: Vector3, target?: Entity, ability?: Ability\|integer, ignore_team?: boolean, radius?: number) -> boolean` | safe | A box of +-radius swept from `from` to `pos` through the local pawn reaches `pos` or stops on `target`; teammates pass through it with ignore_team. radius defaults to the ability's projectile hull (its physics radius, else its weapon's bullet radius vs the world). false for a radius outside (0, 1e5] and off the game thread. CHANGED: registered again (it was documented but not installed). |
| `throwable_aim` | `HERO_LIB.throwable_aim(with_arc?: boolean) -> table\|nil` | safe | The ability or throwable item the local hero is aiming, from the producer the projectile visuals read: { active, generation, ability (entity index), ability_hash, slot, origin, landing, normal, radius, flight_time (seconds), distance (units), hits_world, arc_count }; nil while nothing is aimed. with_arc adds arc = { Vector3, ... } (one table per point). arc_count 0: the ability has no projectile and landing is the placement point. |
| `threat` | `HERO_LIB.threat(kind?: string) -> table\|nil` | safe | The live threat that concerns the local hero (a modifier on it, or an enemy cast within reach) with the nearest answer point, from the threat feed the counter-spell detector fills: { id (unique per threat), kind ("ult", "cc" or "other"), cc, ult (an ultimate that stuns is both), source (the enemy's entity index, -1 unknown), eta_ms (until the detector's answer point, 0 once reached), hit_ms (until the hit lands, >= eta_ms, 0 once it has), slot (the source ability's signature slot 0-3; -1 item or unknown), projectile (entity index of the projectile for a projectile threat, -1 otherwise), age_ms (since detection), ability (the detector key, e.g. "infernus_ult"; "projectile" for a projectile with no Counter Spell row of its own), on_me, answered, enabled (the user's Counter Spell row for the key) }; nil when there is none. kind "cc" or "ult" keeps only threats of that class; any other string raises. A threat stays live until 800 ms past its answer point. Each call keeps the detector armed for about 2 s. While the Auto Dodge feed is armed (HERO_LIB.dodger_arm) projectile threats are included. Any thread. CHANGED: hit_ms, slot, projectile and enabled are new, and projectile rows appear. A row also carries cast (an enemy's cast of a signature ability seen in its cast state: in its cast delay, hit_ms until the cast goes off plus the projectile's flight; in a channel or just gone out, hit_ms 0; false once a detector row or the projectile pick of the same ability takes the row over, keeping its id and answered state), end_ms (until the effect window ends: a channel, the caster's own buff, or the hit of a cast that lands inside its cast delay; 0 once it has; nil when the row has none) and launch_ms (until the cast leaves its cast delay, negative once it has; nil when the row has none). The native projectile pick's row carries its path in Umbrella's threat shape, as threats() describes. projectile is -1 for an ability bullet, which has no entity; ability is "cast" for a cast the detector has no key for. |
| `threat_answer` | `HERO_LIB.threat_answer(id: integer, gate_ok: boolean, lead_s: number?) -> boolean` | safe | Safety's reaction delay for answering threat id (the latch Counter Spell's responses use): call it every tick the answer is due, with gate_ok the action gate's verdict for the pressing action; true once that has held for the sampled human delay (at once with Safety off), and from then on the threat reads answered = true for every reader. false off the game thread and for an id no longer in the feed (the 8 newest are kept); a non-integer id raises. lead_s (default 0) is read as the answer's lead in seconds. |
| `predict_lead_point` | `HERO_LIB.predict_lead_point(target: PlayerPawn, ability_or_speed: Ability\|number, info_from?: integer, hitbox_bits?: integer, radius_override?: number, backtrack?: boolean) -> Vector3\|nil, boolean` | safe | With an ability: the projectile solve's aim point on the target (info_from ENUM_PPS_INFO_FROM, default 1 GUN; hitbox bits as get_hitbox_aim takes them); with backtrack the target point starts at its backtrack record (the aim preset's window), and the second result says whether a record was used. With a speed: the constant-velocity lead of the target's torso from the local eye. |
| `simulate_pawn_movement` | `HERO_LIB.simulate_pawn_movement(target: PlayerPawn, sim_type?: integer, ticks_or_stop?: integer\|function) -> Vector3[]\|nil` | safe | The pawn's position after each game tick; nil without a pawn the newest frame holds. sim_type ENUM_MV_SIM_TYPE.SIMULATE_MOVEMENT (0, the default) runs the aimbot's target movement: air control and drag, sv_gravity times the pawn's gravity scale, landing on and sliding along the map; SIMPLE (1) follows the velocity. A number is the tick count (default 1, at most 256 and 4.8 s); a function is called with (position, tick, velocity, on_ground) after each tick and ends the run by returning true. |
| `simulate_movement_for_duration` | `HERO_LIB.simulate_movement_for_duration(target: PlayerPawn, duration: number, sim_type?: integer) -> Vector3\|nil` | safe | Where simulate_pawn_movement's sim puts the pawn after duration seconds (at most 4.8 s), with its velocity and its ground flag then; nil without a pawn the newest frame holds. |
| `rotate_movement` | `HERO_LIB.rotate_movement(vec: Vector3, degrees: number) -> Vector3\|nil` | safe | vec turned about the vertical axis by degrees, counter-clockwise seen from above (the yaw convention); nil when vec is not a vector. |
| `is_untargetable` | `HERO_LIB.is_untargetable(pawn: PlayerPawn) -> boolean` | safe | TECH_UNTARGETABLE_BY_ENEMIES state OR any invulnerability modifier (Ethereal Shift, Haze phase-out, Viscous cube, Wrecker, Metal Skin, Prism Blast, Vyper ult, ...). The modifier names make it work on enemies. State bit and modifier flags come from this tick's EntityFrame snapshot (once per tick; false for a pawn the frame does not hold). |
| `is_stunned` | `HERO_LIB.is_stunned(pawn?: PlayerPawn) -> boolean` | safe | STUNNED state of the pawn (default: local pawn). is_stunned, is_silenced, is_frozen, is_disabled, is_state_enabled and every is_<state> / has_<state> / <state>_disabled accessor read this tick's EntityFrame state mask: refreshed once per tick, all clear for a pawn the frame does not hold or holds dead or dormant. |
| `is_in_ethereal_shift` | `HERO_LIB.is_in_ethereal_shift(pawn: PlayerPawn) -> boolean` | safe | The Ethereal Shift bubble modifier is on this pawn (by modifier name, so it works on enemies). CHANGED: used to test the INVULNERABLE state, which matched any invulnerability and missed the shift when that bit was absent. |
| `has_los` | `HERO_LIB.has_los(pawn: PlayerPawn) -> boolean` | safe | Line of sight from your eye to the pawn's head (+64) or body centre (+40). Clear only when the trace hits the pawn or travels more than 99.9% of the way. Does not yet honour smoke or other LoS-only blockers. CHANGED: the feet probe and the 97% tolerance are gone. |
| `get_ability` | `HERO_LIB.get_ability(slot: integer, pawn?: PlayerPawn) -> lightuserdata\|nil` | safe | The ability in this EAbilitySlots_t slot (0..3 = ability 1..4, 4..7 = active items, 21 = primary weapon) on pawn (default: local pawn), as light userdata every HERO_LIB ability function accepts. CHANGED: used to index the ability vector. |
| `get_item` | `HERO_LIB.get_item(slot: integer) -> lightuserdata\|nil` | safe | The local hero's active item in slot 4..7, else nil. CHANGED: used to accept vector indices 4..15. |
| `aim_psilent_default` | `HERO_LIB.aim_psilent_default(cmd: UserCmd, target_pos: Vector3, ...) -> boolean` | safe | Optional trailing Ability names the cast (bus owner + early release). |
| `aim_psilent` | `HERO_LIB.aim_psilent(cmd: UserCmd, target_pos: Vector3, ...) -> boolean` | safe | aim_psilent(cmd, smooth, pos, target, _, mode, slot, [should_cancel], [on_fire], [ability]). mode: true or non-zero is PSilent, 2 is PSilent with the visible aim driven underneath, false or 0 is the visible aim only. slot 0..3 presses that ability; without one the step only aims. should_cancel() returns true to continue the step; false stops it. |
| `psilent_bus_settled` | `HERO_LIB.psilent_bus_settled() -> boolean` | safe | PSilent camera is free: no cast in flight. Gate a combo step on it. |
| `cast_ability` | `HERO_LIB.cast_ability(cmd: UserCmd, ability: Ability\|integer, alt_cast?: boolean, confirm_attack?: boolean, slot_override?: integer) -> boolean` | safe | One step of casting the ability by the player's casting mode. Instant / Quick: pulse the slot's button, or release it while the ability is already selected (the release casts it). Confirm: pulse the button to select, then the Fire edge when confirm_attack. alt_cast holds the alternate-cast button; slot_override presses that slot's button instead. The older cast_ability(slot) form works on this tick's command. false when the slot has no button or nothing was pressed or released this tick. CHANGED: it used to press the slot bit only. |
| `is_heavy_melee` | `HERO_LIB.is_heavy_melee(pawn: PlayerPawn) -> boolean` | safe | True while this pawn is mid heavy-melee. Checks the modifier STATE first (works on ENEMIES), then falls back to the HoldMelee ability's attack type/state (more precise, but only ever populated for the LOCAL/spectated player — see is_heavy_melee_charging). |
| `is_heavy_melee_charging` | `HERO_LIB.is_heavy_melee_charging(pawn: PlayerPawn) -> boolean` | safe | True while this pawn is winding up / dashing a HEAVY melee. THE signal to arm an auto-parry on, and the only one that works on ENEMIES. Derived from the entity frame's modifier state (state mask) (MODIFIER_STATE_IS_IN_CHARGE_MELEE=299 / IN_SLIDE_CHARGED_MELEE_ATTACK=199, both verified against the live client.dll enum table). Do NOT use HERO_LIB.melee_state().type/.state for an enemy: those fields are MNetworkUserGroup='LocalPlayerOwnerAndObserversExclusive', i.e. the server only sends them to the ability's OWNER and that owner's spectators, so for an enemy they read 0/None forever at a perfectly correct offset. Every other field on CCitadel_Ability_HoldMelee (m_flStateStartTime, m_flDashStartTime, m_nLightChainCount) has the same user group, and m_bCreatedChargeEffects/m_angForced/m_vGoalDir are not networked at all — there is no readable field alternative. |
| `modifier_state_bits` | `HERO_LIB.modifier_state_bits(pawn?: PlayerPawn) -> integer` | safe | DIAGNOSTIC: modifier states 0-31 of the pawn (default: local pawn) as one bitmask, from this tick's EntityFrame state mask (refreshed once per tick; 0 for a pawn the frame does not hold or holds dead or dormant). enabled_state_bits lists every enabled ordinal. |
| `modifier_remaining` | `HERO_LIB.modifier_remaining(pawn: PlayerPawn?, name: string) -> number` | safe | Seconds left on the named modifier of the pawn (default: local pawn), counted from its last (re)application, else from its creation; -1 when it has no duration, 0 when the pawn does not carry it. |
| `modifier_is_debuff` | `HERO_LIB.modifier_is_debuff(pawn: PlayerPawn?, name: string) -> boolean` | safe | The named modifier is a debuff on the pawn (default: local pawn). false when the vdata or the teams cannot say; a missing team field reads as unknown, never as team 0. |
| `modifier_is_hidden` | `HERO_LIB.modifier_is_hidden(pawn: PlayerPawn?, name: string) -> boolean` | safe | The named modifier is hidden per its vdata. "Hidden if the caster is the target" counts only when the pawn cast it on itself; a hidden flag without a readable hidden type counts as hidden. |
| `modifier_is_purgeable` | `HERO_LIB.modifier_is_purgeable(pawn: PlayerPawn?, name: string) -> boolean` | safe | The named modifier can be purged unless an attribute says otherwise; false when its vdata attributes cannot be read. |
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
| `passive_items` | `HERO_LIB.passive_items() -> boolean` | safe | Returns a 1-indexed table of ability lightuserdata for every ability on the pawn whose vdata has m_bShowInPassiveItemsArea set; defaults to the local pawn when no pawn is passed. |
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
| `headshot_cap_ok` | `HERO_LIB.headshot_cap_ok(max_percent: number) -> boolean` | safe | May a script aim at the HEAD right now? The same stat test the aimbot's own bone selection applies (CanTargetHeadBasedOnDamageStats); false => drop Head+Neck from the mask. Never raises: the bundled aim library calls it without pcall. |
| `vdata_property` | `HERO_LIB.vdata_property(ability: Ability, vdata_class: string, field: string) -> number\|nil` | safe | A float field on the ability's VDATA, by schema CLASS + NAME (e.g. "CAbilityHornetSnipeVData", "m_flMinScopeTimeToShoot"). ability:get_vdata() only projects m_projectileInfo/m_WeaponInfo, so every other authored VData number is unreachable without this. The class name is explicit because a VData object carries no schema binding to ask. Offset resolved through the LIVE schema. nil = unknown class/field. |
| `maybe_light_melee` | `HERO_LIB.maybe_light_melee(cmd: UserCmd, chance: number, key?: string) -> boolean` | safe | Roll-once light-melee humanizer. |
| `reset_light_melee` | `HERO_LIB.reset_light_melee(key: string)` | safe | Open a fresh melee roll window. |
| `press_ability` | `HERO_LIB.press_ability(cmd: UserCmd, ability: Ability\|integer, alt_cast?: boolean, confirm_attack?: boolean, slot_override?: integer) -> boolean` | safe | Same function as cast_ability. |
| `slot_ability_bit` | `HERO_LIB.slot_ability_bit(slot: integer) -> number` | safe | slot 0..3 -> IN_ABILITYn bit. |
| `meters_to_units` | `HERO_LIB.meters_to_units(m: number) -> number` | safe | Converts a distance in meters to Source-engine units via Math::MetersToUnits. |
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
| `hit_chance_pass` | `HERO_LIB.hit_chance_pass(percent: number) -> boolean` | safe | One roll against a hit chance (the aimbot's per-shot roll): true at >= 100, false at <= 0. Game thread (CreateMove callbacks); elsewhere only a chance that stays certain under Safety's cap passes. |
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
| `counter_chain` | `HERO_LIB.counter_chain(threat: table\|string) -> string[]\|nil, string, boolean` | safe | Counter Spell's answer for a threat() / threats() row or its `ability` key: chain (the response ids to try in order, e.g. "parry", "metal_skin"; empty when nothing answers it), mode ("always" \| "if_lethal" \| "never"), fallback (true when chain is the Any-threat chain because the threat has none of its own). nil while Counter Spell is off. Any thread, lock-free. A threat row answers to its threat's own Counter Spell cell while the threat is in the feed (a projectile carries the cell of the hero ability that fired it, which its key alone may not name); a key, or a row whose threat has left the feed, answers to the key's cell, and a key with no cell of its own takes the Any-threat chain. Nothing native presses the chain: the answering script (dodger.lua) is Counter Spell's one executor. |
| `dodger_arm` | `HERO_LIB.dodger_arm(on: boolean)` | safe | Arms (true or a non-zero number) or disarms the Auto Dodge feed: the bundled dodger.lua calls it on its switch, so projectile buckets are walked only while the row is on. While armed, threat() and threats() include projectile threats. |
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
| `lead_for` | `HERO_LIB.lead_for(from: Vector3, pos: Vector3, vel: Vector3, speed: number, ability?: Ability, ignore_z?: boolean) -> Vector3, Vector3, number` | safe | The straight-line intercept: aim, predicted, t. With an ability its projectile supplies the speed when speed is not positive, and unless ignore_z the aim point is raised by the drop (0.5 g t^2), lowered by its up speed and by its vertical aim bias. Without a speed or an intercept, aim = predicted = pos and t = 0. The vertical aim bias is spread over the horizontal distance. |
| `SLOT.ABILITY_1` | `.SLOT.ABILITY_1: integer` | safe | Slot index of the hero's first signature ability. |
| `ability_cd_remaining` | `HERO_LIB.ability_cd_remaining(ability: Ability\|integer) -> number` | safe | Seconds remaining on the ability's cooldown; 0 if the handle is missing. |
| `ability_index_slot` | `HERO_LIB.ability_index_slot(ability: Ability\|integer) -> integer` | safe | Returns the ability's data-table index, or 0 if the handle is missing. |
| `iter_abilities` | `HERO_LIB.iter_abilities(pawn: PlayerPawn?) -> table` | safe | Array of ability userdata walked from the pawn (local pawn when omitted); empty if the pawn is missing. |
| `ability_charges` | `HERO_LIB.ability_charges(ability: Ability\|integer) -> integer` | safe | Remaining charges on the ability (m_iRemainingCharges); 0 if the handle is missing. |
| `ability_range` | `HERO_LIB.ability_range(ability: Ability) -> number` | safe | Effective cast range of the ability in units; 0 if the handle is missing. |
| `is_ability_slot` | `HERO_LIB.is_ability_slot(slot: integer) -> boolean` | safe | True when the slot index falls within the signature-ability range. |
| `QUICKCAST_MODE.INSTANT` | `.QUICKCAST_MODE.INSTANT: integer` | safe | Quickcast mode that fires the ability on key press without a confirmation step. |
| `ENUM_MV_SIM_TYPE.SIMPLE` | `.ENUM_MV_SIM_TYPE.SIMPLE: integer` | safe | Movement-sim mode selecting the lightweight linear predictor instead of the full movement simulation. |
| `combo_engine` | `HERO_LIB.combo_engine(engine_id: integer?)` | safe | Declares the combo-engine id for the running script's VM; a non-positive or missing value clears it. |
| `get_slide_level` | `HERO_LIB.get_slide_level() -> integer` | safe | Current slide intensity of the local pawn: 2 while the predicted state is sliding, otherwise the measured slide level (0 when not sliding). |
| `modifier_ability_entity` | `HERO_LIB.modifier_ability_entity(pawn: PlayerPawn?, name: string) -> Entity\|nil` | safe | Entity resolved from the modifier's m_hAbility handle, or nil if the pawn has no such modifier. |
| `perf_begin` | `HERO_LIB.perf_begin()` | safe | Legacy compatibility stub that does nothing. |
| `version` | `.version: integer` | safe | HERO_LIB API version (currently 2). |
| `INNATE.ZIPLINE` | `.INNATE.ZIPLINE: integer` | safe | Innate-action index for the zipline action. |
| `game_focused` | `HERO_LIB.game_focused() -> boolean` | safe | True while the game window has input focus. |
| `is_grey_talon` | `HERO_LIB.is_grey_talon() -> boolean` | safe | True when the local hero is Grey Talon. |
| `is_mo_krill` | `HERO_LIB.is_mo_krill() -> boolean` | safe | True when the local hero is Mo & Krill. |
| `local_eye_pos` | `HERO_LIB.local_eye_pos() -> Vector3` | safe | Local player's camera eye position; returns a zero vector when the local view is unavailable. |
| `refresh_lp` | `HERO_LIB.refresh_lp() -> PlayerPawn\|nil` | safe | Current local pawn userdata, or nil when it is not resolved. |
| `has_all_modifiers` | `HERO_LIB.has_all_modifiers(pawn: PlayerPawn?, names: table) -> boolean` | safe | True when every string in the list is present on the pawn's modifier list. |
| `sum_modifier_stacks` | `HERO_LIB.sum_modifier_stacks(pawn: PlayerPawn?, names: table) -> integer` | safe | Sum of GetStackCount() across the pawn's modifiers whose name appears in the list. |
| `MOD_STATE.DAMAGE_MOVE_PENALTY_IMMUNE` | `.MOD_STATE.DAMAGE_MOVE_PENALTY_IMMUNE: integer` | safe | Live modifier-state bit for DAMAGE_MOVEMENT_PENALTY_IMMUNE. |
| `MOD_STATE.ENTERING_VEHICLE` | `.MOD_STATE.ENTERING_VEHICLE: integer` | safe | Live modifier-state bit for ENTERING_VEHICLE. |
| `MOD_STATE.IGNORED_BY_NPC_TARGETING` | `.MOD_STATE.IGNORED_BY_NPC_TARGETING: integer` | safe | Live modifier-state bit for IGNORED_BY_NPC_TARGETING. |
| `MOD_STATE.IN_MID_BOSS_TEMPLE` | `.MOD_STATE.IN_MID_BOSS_TEMPLE: integer` | safe | Live modifier-state bit for IN_MID_BOSS_TEMPLE. |
| `MOD_STATE.OUT_OF_GAME` | `.MOD_STATE.OUT_OF_GAME: integer` | safe | Live modifier-state bit for OUT_OF_GAME. |
| `MOD_STATE.SPRINTING` | `.MOD_STATE.SPRINTING: integer` | safe | Live modifier-state bit for SPRINTING. |
| `MOD_STATE.UNKILLABLE` | `.MOD_STATE.UNKILLABLE: integer` | safe | Live modifier-state bit for UNKILLABLE. |
| `dash_disabled` | `HERO_LIB.dash_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DASH_DISABLED modifier state. |
| `has_infinite_clip` | `HERO_LIB.has_infinite_clip(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the INFINITE_CLIP modifier state. |
| `is_blind` | `HERO_LIB.is_blind(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the BLIND modifier state. |
| `is_dash_disabled` | `HERO_LIB.is_dash_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DASH_DISABLED modifier state. |
| `is_dmg_move_penalty_immune` | `HERO_LIB.is_dmg_move_penalty_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DAMAGE_MOVEMENT_PENALTY_IMMUNE modifier state. |
| `is_ignored_by_npc_target` | `HERO_LIB.is_ignored_by_npc_target(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IGNORED_BY_NPC_TARGETING modifier state. |
| `is_in_mid_boss_temple` | `HERO_LIB.is_in_mid_boss_temple(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IN_MID_BOSS_TEMPLE modifier state. |
| `is_material_override` | `HERO_LIB.is_material_override(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MATERIAL_OVERRIDE modifier state. |
| `is_parry_disabled` | `HERO_LIB.is_parry_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the PARRY_DISABLED modifier state. |
| `is_sliding` | `HERO_LIB.is_sliding(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SLIDING modifier state. |
| `is_tech_damage_immune` | `HERO_LIB.is_tech_damage_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the TECH_DAMAGE_INVULNERABLE modifier state. |
| `is_wallsliding` | `HERO_LIB.is_wallsliding(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the WALLSLIDE modifier state. |
| `silence_movement_abilities` | `HERO_LIB.silence_movement_abilities(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SILENCE_MOVEMENT_ABILITES modifier state. |
| `TEAM.UNASSIGNED` | `.TEAM.UNASSIGNED: integer` | safe | Team-id value for pawns that have not been assigned to a team. |
| `hp_ratio` | `HERO_LIB.hp_ratio(pawn: PlayerPawn) -> number` | safe | Pawn health as a 0..1 fraction of max health; 0 when the pawn is missing or has no readable facts. |
| `is_zoomed` | `HERO_LIB.is_zoomed(pawn: PlayerPawn?) -> boolean` | safe | True when the pawn's weapon is scoped/zoomed in the current frame. |
| `pawn_info` | `HERO_LIB.pawn_info(pawn: PlayerPawn?) -> table` | safe | Snapshot of the pawn's facts (index, hp, max_hp, team, life_state, alive, max_move_speed, speed, flags); an empty table when the pawn has no readable facts. |
| `predict_position_v2` | `HERO_LIB.predict_position_v2(pawn: PlayerPawn, t: number?) -> Vector3\|nil` | safe | Pawn origin extrapolated by velocity * t seconds (t defaults to 0); nil if the pawn has no readable facts. |
| `allies_alive` | `HERO_LIB.allies_alive() -> table` | safe | Array of alive ally pawn userdata relative to the local player; empty when the local player is invalid. |
| `count_enemies_in_radius` | `HERO_LIB.count_enemies_in_radius(center: Vector3?, radius: number?) -> integer` | safe | Count of enemy heroes within radius (default 1000 units) of center; defaults to the local pawn's position when no center is given. |
| `nearest_deployable` | `HERO_LIB.nearest_deployable() -> Vector3\|nil` | safe | Origin of the nearest deployable entity to the local pawn, or nil when none are in frame. |
| `angles_to_forward` | `HERO_LIB.angles_to_forward(pitch: number?, yaw: number?) -> Vector3` | safe | Forward vector derived from pitch and yaw (degrees); omitted components default to 0. |
| `distance_between` | `HERO_LIB.distance_between(a: Vector3\|PlayerPawn, b: Vector3\|PlayerPawn) -> number` | safe | 3D distance in units between two points, or between two pawns' origins when vectors are not supplied; 0 if either operand is missing. |
| `pos_add` | `HERO_LIB.pos_add(a: Vector3, b: Vector3) -> Vector3\|nil` | safe | Returns a + b, or nil if either argument is not a Vector3. |
| `pos_scale` | `HERO_LIB.pos_scale(a: Vector3, k: number?) -> Vector3\|nil` | safe | Returns a scaled by k (defaults to 1), or nil if a is not a Vector3. |
| `SLOT.ABILITY_2` | `.SLOT.ABILITY_2: integer` | safe | Ability slot id for the hero's second signature ability. |
| `ability_channeling` | `HERO_LIB.ability_channeling(ability: Ability\|integer) -> boolean` | safe | True while the ability's raw `m_bChanneling` flag is set; false when the ability is missing. |
| `ability_ready_count` | `HERO_LIB.ability_ready_count() -> integer` | safe | Number of the local pawn's four signature abilities that are currently ready. |
| `min_ability_cooldown` | `HERO_LIB.min_ability_cooldown(slots: table) -> number` | safe | Smallest remaining cooldown across the given local-pawn ability slot indices; returns the never-ready sentinel when no slot matches. |
| `ability_charges_raw` | `HERO_LIB.ability_charges_raw(ability: Ability\|integer) -> integer` | safe | Raw `m_iRemainingCharges` for the ability; 0 when the ability is absent. |
| `ability_spirit_cost` | `HERO_LIB.ability_spirit_cost(ability: Ability) -> number` | safe | Scaled `AbilityResourceCost` for the ability (its spirit/resource cost); 0 when absent. |
| `is_item_slot` | `HERO_LIB.is_item_slot(slot: integer) -> boolean` | safe | True when the slot index falls within the active-item slot range. |
| `QUICKCAST_MODE.QUICK` | `.QUICKCAST_MODE.QUICK: integer` | safe | Quickcast-mode constant selecting the quick-cast (press-to-fire without a confirmation click) behaviour. |
| `ENUM_MV_SIM_TYPE.SIMULATE_MOVEMENT` | `.ENUM_MV_SIM_TYPE.SIMULATE_MOVEMENT: integer` | safe | Movement-simulation mode constant selecting the full movement-physics path (as opposed to the simple linear fallback). |
| `combo_key` | `HERO_LIB.combo_key(vk: integer\|nil) -> boolean,boolean` | safe | Reports whether the combo hotkey (optional virtual-key override, 0 for the default) is currently held, plus a second boolean set when the held state has just changed. |
| `has_incoming_ability` | `HERO_LIB.has_incoming_ability() -> boolean` | safe | Compatibility stub; always returns false. |
| `modifier_caster_entity` | `HERO_LIB.modifier_caster_entity(pawn: PlayerPawn\|nil, name: string) -> Entity\|nil` | safe | Entity that applied the named modifier on the pawn (defaults to the local pawn); nil when the modifier is absent or its caster handle no longer resolves. |
| `perf_end` | `HERO_LIB.perf_end()` | safe | Compatibility stub; does nothing. |
| `world_to_screen` | `HERO_LIB.world_to_screen(pos: Vector3) -> number\|nil,number\|nil` | safe | Projects a world position to screen x,y coordinates; returns nil,nil when the input is not a Vector3 or the projection fails. |
| `item_count` | `HERO_LIB.item_count(pawn: PlayerPawn\|nil) -> integer` | safe | Count of the pawn's abilities that are items (defaults to the local pawn). |
| `get_eye_pos` | `HERO_LIB.get_eye_pos() -> Vector3\|nil` | safe | Local pawn's eye position from the current frame; nil when the local view is not available. |
| `is_haze` | `HERO_LIB.is_haze() -> boolean` | safe | True when the local hero is Haze. |
| `is_pocket` | `HERO_LIB.is_pocket() -> boolean` | safe | True when the local hero is Pocket. |
| `local_eye_pos_helper` | `HERO_LIB.local_eye_pos_helper() -> Vector3` | safe | Local view eye position, falling back to the zero vector when the local view is unavailable. |
| `stamina` | `HERO_LIB.stamina() -> number\|nil` | safe | Local pawn's current stamina from the action state; nil when the local pawn is missing or stamina is not tracked. |
| `has_any_modifier` | `HERO_LIB.has_any_modifier(pawn: PlayerPawn\|nil, names: table) -> boolean` | safe | True when the pawn (defaults to local) carries any modifier whose name matches one in the given string list (up to 32 names). |
| `MOD_STATE.ADDITIONAL_AIR_MOVES` | `.MOD_STATE.ADDITIONAL_AIR_MOVES: integer` | safe | Live modifier-state bit for ADDITIONAL_AIR_MOVES. |
| `MOD_STATE.DASH_DISABLED` | `.MOD_STATE.DASH_DISABLED: integer` | safe | Live modifier-state bit for DASH_DISABLED. |
| `MOD_STATE.ETHEREAL` | `.MOD_STATE.ETHEREAL: integer` | safe | Live modifier-state bit for ETHEREAL (the game's INVULNERABLE state). |
| `MOD_STATE.IGNORED_BY_UNIT_FILTER` | `.MOD_STATE.IGNORED_BY_UNIT_FILTER: integer` | safe | Live modifier-state bit for IGNORED_BY_UNIT_FILTER. |
| `MOD_STATE.IN_SHOP` | `.MOD_STATE.IN_SHOP: integer` | safe | Live modifier-state bit for IN_SHOP. |
| `MOD_STATE.SHOOTING_DISABLED` | `.MOD_STATE.SHOOTING_DISABLED: integer` | safe | Live modifier-state bit for SHOOTING_DISABLED. |
| `MOD_STATE.SPRINT_DISABLED` | `.MOD_STATE.SPRINT_DISABLED: integer` | safe | Live modifier-state bit for SPRINT_DISABLED. |
| `MOD_STATE.UNLIMITED_AIR_DASHES` | `.MOD_STATE.UNLIMITED_AIR_DASHES: integer` | safe | Live modifier-state bit for UNLIMITED_AIR_DASHES. |
| `dash_disabled_debuff` | `HERO_LIB.dash_disabled_debuff(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DASH_DISABLED_DEBUFF modifier state. |
| `has_unlimited_air_dashes` | `HERO_LIB.has_unlimited_air_dashes(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the UNLIMITED_AIR_DASHES modifier state. |
| `is_bullet_invulnerable` | `HERO_LIB.is_bullet_invulnerable(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the BULLET_INVULNERABLE modifier state. |
| `is_dash_disabled_debuff` | `HERO_LIB.is_dash_disabled_debuff(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DASH_DISABLED_DEBUFF modifier state. |
| `is_entering_vehicle` | `HERO_LIB.is_entering_vehicle(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the ENTERING_VEHICLE modifier state. |
| `is_ignored_by_npc_targeting` | `HERO_LIB.is_ignored_by_npc_targeting(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IGNORED_BY_NPC_TARGETING modifier state. |
| `is_in_shop` | `HERO_LIB.is_in_shop(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IN_SHOP modifier state. |
| `is_melee_attacks_only` | `HERO_LIB.is_melee_attacks_only(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MELEE_ATTACKS_ONLY modifier state. |
| `is_reload_disabled` | `HERO_LIB.is_reload_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the RELOAD_DISABLED modifier state. |
| `is_sliding_slow_getup` | `HERO_LIB.is_sliding_slow_getup(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SLIDING_SLOW_GETUP modifier state. |
| `is_tech_untargetable_by_enemies` | `HERO_LIB.is_tech_untargetable_by_enemies(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the TECH_UNTARGETABLE_BY_ENEMIES modifier state. |
| `items_disabled` | `HERO_LIB.items_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the ITEMS_DISABLED modifier state. |
| `sliding_slow_getup` | `HERO_LIB.sliding_slow_getup(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SLIDING_SLOW_GETUP modifier state. |
| `dist_between` | `HERO_LIB.dist_between(a: PlayerPawn, b: PlayerPawn) -> number` | safe | 3D unit distance between the two pawns' tick origins; 0 when either pawn is missing. |
| `is_ally` | `HERO_LIB.is_ally(pawn: PlayerPawn) -> boolean` | safe | True when the given pawn's frame relation to the local pawn is Ally. |
| `local_team` | `HERO_LIB.local_team() -> integer` | safe | Team number of the local pawn from the current facts; -1 when the local pawn or its facts are unavailable. |
| `pawn_life_state` | `HERO_LIB.pawn_life_state(pawn: PlayerPawn) -> integer` | safe | The pawn's `m_lifeState` from frame facts, or the no-life-state sentinel when facts cannot be read. |
| `predict_self_position` | `HERO_LIB.predict_self_position(dt: number\|nil) -> Vector3` | safe | Predicted local-pawn origin after `dt` seconds of linear motion at current velocity; zero vector when local facts are unavailable. |
| `allies_in_radius` | `HERO_LIB.allies_in_radius(center: Vector3\|nil, radius: number\|nil) -> table` | safe | Light-userdata list of allied pawns whose record origin lies within `radius` (default 1000 units) of `center` (defaults to local origin); empty table when the local view is invalid. |
| `dist_to_local` | `HERO_LIB.dist_to_local(pawn: PlayerPawn) -> number` | safe | 3D unit distance from the local pawn's tick origin to the target pawn's; 0 when either side is missing. |
| `nearest_enemies_sorted` | `HERO_LIB.nearest_enemies_sorted(count: integer\|nil, radius: number\|nil) -> table` | safe | Up to `count` (default 5, clamped to 1..32) nearest opposed pawns within `radius` (default 4000 units), sorted ascending by frame distance. |
| `approx_eq` | `HERO_LIB.approx_eq(a: number\|nil, b: number\|nil, eps: number\|nil) -> boolean` | safe | True when `\|a - b\|` is at most `eps` (default 1e-4); missing numeric args default to 0. |
| `distance_meters` | `HERO_LIB.distance_meters(a: Vector3\|PlayerPawn, b: Vector3\|PlayerPawn) -> number` | safe | Distance in meters between two Vector3 points, or between two pawns' tick origins; 0 when the pair cannot be resolved. |
| `pos_cross` | `HERO_LIB.pos_cross(a: Vector3, b: Vector3) -> Vector3\|nil` | safe | Cross product `a × b`; nil when either argument is not a Vector3. |
| `pos_sub` | `HERO_LIB.pos_sub(a: Vector3, b: Vector3) -> Vector3\|nil` | safe | Vector `a - b`; nil when either argument is not a Vector3. |
| `SLOT.ABILITY_3` | `.SLOT.ABILITY_3: integer` | safe | Slot id for the hero's third signature ability (ESlot_Signature_3). |
| `ability_channeling_raw` | `HERO_LIB.ability_channeling_raw(ability: Ability\|integer) -> boolean` | safe | Raw m_bChanneling flag on the ability (resolved from an ability userdata or slot); false if the ability is nil. |
| `any_ability_ready` | `HERO_LIB.any_ability_ready() -> boolean` | safe | True when at least one of the local pawn's four signature abilities is currently ready. |
| `ready_ability_slots` | `HERO_LIB.ready_ability_slots() -> table` | safe | Array of the input slot ids (0..3) of the local pawn's signature abilities that are currently ready. |
| `ability_damage` | `HERO_LIB.ability_damage(ability: Ability) -> number` | safe | Scaled 'Damage' property of the ability; 0 if the ability is nil. |
| `ability_stamina_cost` | `HERO_LIB.ability_stamina_cost(ability: Ability) -> number` | safe | Scaled 'AbilityResourceCost' property of the ability; 0 if the ability is nil. |
| `kill_lethality` | `HERO_LIB.kill_lethality(ability: Ability\|integer, target: PlayerPawn, delay: number?, extra_damage: number?) -> table\|nil` | safe | Lethality estimate for landing `ability` on `target` after `delay` seconds, optionally overriding damage with `extra_damage`; returns a table with damage/headshot_bonus/hp/remaining/lethal/valid, or nil when the ability or target is missing. |
| `NEUTRAL_TROOPER_TYPE` | `.NEUTRAL_TROOPER_TYPE: table` | safe | Enum table of neutral trooper tiers (TIER1=1, TIER2=2, TIER3=3), resolved from ENeutralNPCType with those as fallback values. |
| `ENUM_PPS_AIM_TO_POS.LIB_TARGET_POS` | `.ENUM_PPS_AIM_TO_POS.LIB_TARGET_POS: integer` | safe | `aim_to` cast-options value that aims the cast at the library's chosen target position (body point) rather than the pawn origin. |
| `combo_report_end` | `HERO_LIB.combo_report_end(hero: integer?, steps: integer?, reason: string?)` | safe | Dev-build hook that reports the end of a combo run with the hero id, step count, and reason string; non-integer hero becomes -1, non-integer steps becomes 0, nil reason becomes '?'. |
| `is_in_ivy_stone_form` | `HERO_LIB.is_in_ivy_stone_form(pawn: PlayerPawn?) -> boolean` | safe | True when the pawn is Ivy currently in Stone Form; reads the Tengu StoneForm ability's m_bInStoneForm when on the game thread. |
| `modifier_elapsed` | `HERO_LIB.modifier_elapsed(pawn: PlayerPawn?, name: string?) -> number` | safe | Seconds since the named modifier started on the pawn, clamped to >= 0; 0 if the modifier is missing or has no recorded start time. |
| `predict_intercept_arc` | `HERO_LIB.predict_intercept_arc(origin: Vector3, speed: number?, gravity: number?, target_pos: Vector3, target_vel: Vector3) -> Vector3\|nil` | safe | Solves the arc-projectile intercept aim point from `origin` with the given launch speed and gravity against a target moving at `target_vel`; nil if origin or target vectors fail to parse. |
| `INNATE.DASH_JUMP` | `.INNATE.DASH_JUMP: integer` | safe | Innate-action id for Dash Jump (EInnateAction::DashJump). |
| `iter_items` | `HERO_LIB.iter_items(pawn: PlayerPawn?) -> table` | safe | Returns an array of the pawn's item abilities (local pawn if omitted) as light userdata. |
| `get_max_health` | `HERO_LIB.get_max_health() -> integer` | safe | Local pawn's max health; 0 when the pawn is missing or facts are unavailable. |
| `is_holliday` | `HERO_LIB.is_holliday() -> boolean` | safe | True when the local hero id is Holliday. |
| `is_seven` | `HERO_LIB.is_seven() -> boolean` | safe | True when the local hero id is Seven. |
| `local_hero_id` | `HERO_LIB.local_hero_id() -> integer` | safe | Local controller's hero id, or -1 when no controller is bound. |
| `time` | `HERO_LIB.time() -> number` | safe | Current engine game time in seconds. |
| `has_modifier` | `HERO_LIB.has_modifier(pawn: PlayerPawn?, name: string?) -> boolean` | safe | True when the pawn has a modifier whose name exactly matches `name`. |
| `MOD_STATE.AIR_DASHING` | `.MOD_STATE.AIR_DASHING: integer` | safe | Live modifier-state bit for AIR_DASHING. |
| `MOD_STATE.DASH_DISABLED_DEBUFF` | `.MOD_STATE.DASH_DISABLED_DEBUFF: integer` | safe | Live modifier-state bit for DASH_DISABLED_DEBUFF. |
| `MOD_STATE.EXITING_VEHICLE` | `.MOD_STATE.EXITING_VEHICLE: integer` | safe | Live modifier-state bit for EXITING_VEHICLE. |
| `MOD_STATE.IMMOBILIZED` | `.MOD_STATE.IMMOBILIZED: integer` | safe | Live modifier-state bit for IMMOBILIZED. |
| `MOD_STATE.ITEMS_DISABLED` | `.MOD_STATE.ITEMS_DISABLED: integer` | safe | Live modifier-state bit for ITEMS_DISABLED. |
| `MOD_STATE.SHOOTING_FORCED_ON` | `.MOD_STATE.SHOOTING_FORCED_ON: integer` | safe | Live modifier-state bit for SHOOTING_FORCED_ON. |
| `MOD_STATE.SPRINT_NO_INTERRUPT` | `.MOD_STATE.SPRINT_NO_INTERRUPT: integer` | safe | Live modifier-state bit for SPRINT_NO_INTERRUPT. |
| `MOD_STATE.UNLIMITED_AIR_JUMPS` | `.MOD_STATE.UNLIMITED_AIR_JUMPS: integer` | safe | Live modifier-state bit for UNLIMITED_AIR_JUMPS. |
| `disable_gravity` | `HERO_LIB.disable_gravity(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISABLE_GRAVITY modifier state. |
| `has_unlimited_air_jumps` | `HERO_LIB.has_unlimited_air_jumps(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the UNLIMITED_AIR_JUMPS modifier state. |
| `is_burning` | `HERO_LIB.is_burning(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the BURNING modifier state. |
| `is_deaf` | `HERO_LIB.is_deaf(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DEAF modifier state. |
| `is_exiting_vehicle` | `HERO_LIB.is_exiting_vehicle(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the EXITING_VEHICLE modifier state. |
| `is_ignored_by_unit_filter` | `HERO_LIB.is_ignored_by_unit_filter(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IGNORED_BY_UNIT_FILTER modifier state. |
| `is_invis_enemy_on_cast` | `HERO_LIB.is_invis_enemy_on_cast(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the INVISIBLE_TO_ENEMY_CAST modifier state. |
| `is_melee_disabled` | `HERO_LIB.is_melee_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MELEE_DISABLED modifier state. |
| `is_root_immune` | `HERO_LIB.is_root_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the ROOT_IMMUNE modifier state. |
| `is_slow_immune` | `HERO_LIB.is_slow_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SLOW_IMMUNE modifier state. |
| `is_tech_untargetable_by_teammates` | `HERO_LIB.is_tech_untargetable_by_teammates(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the TECH_UNTARGETABLE_BY_TEAMMATES modifier state. |
| `material_override` | `HERO_LIB.material_override(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MATERIAL_OVERRIDE modifier state. |
| `sprint_disabled` | `HERO_LIB.sprint_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SPRINT_DISABLED modifier state. |
| `dist_squared` | `HERO_LIB.dist_squared(a: PlayerPawn, b: PlayerPawn) -> number` | safe | Squared distance in units between the two pawns' current tick origins; 0 when either pawn is missing. |
| `is_busy_with_action` | `HERO_LIB.is_busy_with_action(pawn: PlayerPawn?, counting_items: boolean?) -> boolean` | safe | True when the pawn is busy with an action; the second boolean asks the native to also count item casts as busy. |
| `max_move_speed` | `HERO_LIB.max_move_speed(pawn: PlayerPawn?) -> number` | safe | Pawn's cached max move speed from its PawnExt record; 0 when the record is unavailable. |
| `pawn_max_health` | `HERO_LIB.pawn_max_health(pawn: PlayerPawn) -> integer` | safe | Max health of the pawn (or an entity record passed in its place); 0 when neither is readable. |
| `same_team` | `HERO_LIB.same_team(a: any, b: any) -> boolean` | safe | True when both arguments resolve to the same non-negative team id. |
| `ally_hp_avg_pct` | `HERO_LIB.ally_hp_avg_pct() -> number` | safe | Mean health fraction (0..1) across living friendly player pawns in the current frame; 0 when there is no local pawn, no allies, or the frame is unstable. |
| `enemies` | `HERO_LIB.enemies() -> table` | safe | Returns an array of up to kMaxListed opposing player pawns (as light userdata) from the current entity frame; empty when there is no local pawn. |
| `nearest_enemy` | `HERO_LIB.nearest_enemy() -> PlayerPawn\|nil` | safe | Closest opposing player pawn to the local pawn in the current frame, or nil when none. |
| `clamp` | `HERO_LIB.clamp(v: number?, lo: number?, hi: number?) -> number` | safe | Clamps v into [lo, hi]; defaults are v=0, lo=0, hi=1. |
| `dot` | `HERO_LIB.dot(a: Vector3, b: Vector3) -> number` | safe | Dot product of two Vector3s; 0 if either argument fails to parse. |
| `pos_delta` | `HERO_LIB.pos_delta(a: Vector3, b: Vector3) -> Vector3\|nil` | safe | Returns b - a as a Vector3; nil if either argument fails to parse. |
| `pos_zero` | `HERO_LIB.pos_zero() -> Vector3` | safe | Zero Vector3 (0, 0, 0). |
| `SLOT.ITEM_1` | `.SLOT.ITEM_1: integer` | safe | Slot id for the first active item. |
| `ability_cooldown_end` | `HERO_LIB.ability_cooldown_end(ability: Ability\|integer) -> number` | safe | Absolute game time at which the ability's current cooldown ends; 0 when the ability is missing. |
| `can_activate_ability` | `HERO_LIB.can_activate_ability(ability: Ability\|integer) -> boolean` | safe | True when the ability passes the engine's activate-ability check. |
| `ability_ammo_cost` | `HERO_LIB.ability_ammo_cost(ability: Ability) -> number` | safe | Ammo consumed per shot by the ability's weapon info; 0 when no weapon info is attached. |
| `ability_is_projectile` | `HERO_LIB.ability_is_projectile(ability: Ability) -> boolean` | safe | True when the ability has a strictly positive projectile speed. |
| `ability_upgrade_level` | `HERO_LIB.ability_upgrade_level(ability: Ability) -> integer` | safe | Current upgrade level of the ability; 0 when the ability is missing. |
| `slot_is_ultimate` | `HERO_LIB.slot_is_ultimate(slot: integer) -> boolean` | safe | True when the slot id is the ultimate (Signature_4) slot. |
| `TROOPER_TYPE` | `.TROOPER_TYPE: table` | safe | Table of trooper-type ids (RANGED, MEDIC, MELEE, ZIPLINE_CONTAINER) resolved from the TrooperType_t enum, with fixed fallbacks when the schema has not resolved. |
| `ENUM_PPS_AIM_TO_POS.PAWN_ORIGIN` | `.ENUM_PPS_AIM_TO_POS.PAWN_ORIGIN: integer` | safe | predict_cast aim-to-position selector that aims at the target pawn's origin. |
| `combo_report_row` | `HERO_LIB.combo_report_row(row: integer, label?: string, outcome?: string, t?: number)` | safe | Dev-build only: records one row (index, label, outcome, time) in the current combo-run report. |
| `is_in_viscous_cube` | `HERO_LIB.is_in_viscous_cube(pawn: PlayerPawn?) -> boolean` | safe | True when the pawn is held in a Viscous cube — frame VISCOUS_CUBED state or the cube mod-flag is set. |
| `modifier_is_aura` | `HERO_LIB.modifier_is_aura(pawn: PlayerPawn?, name: string) -> boolean` | safe | True when the named modifier on the pawn has an aura provider or the AURA_PRIORITY attribute bit. |
| `predict_intercept_linear` | `HERO_LIB.predict_intercept_linear(origin: Vector3, speed: number, target_pos: Vector3, target_vel: Vector3, lead?: number) -> Vector3\|nil` | safe | Firing-solution aim point for hitting a linearly-moving target with a constant-speed projectile; nil when any input vector can't be read. |
| `INNATE.HEAVY_MELEE` | `.INNATE.HEAVY_MELEE: integer` | safe | Innate-action id for heavy melee. |
| `owns_item_slot` | `HERO_LIB.owns_item_slot(slot: integer) -> boolean` | safe | True when the local pawn holds an ability in the given active-item slot. |
| `health` | `HERO_LIB.health() -> integer` | safe | Local pawn's current health, 0 when its facts are unavailable. |
| `is_infernus` | `HERO_LIB.is_infernus() -> boolean` | safe | True when the local hero is Infernus. |
| `is_shiv` | `HERO_LIB.is_shiv() -> boolean` | safe | True when the local hero is Shiv. |
| `local_view_dir` | `HERO_LIB.local_view_dir() -> Vector3` | safe | Local player's view direction; falls back to {1,0,0} when the local view is invalid. |
| `time_now` | `HERO_LIB.time_now() -> number` | safe | Current game time in seconds. |
| `has_modifier_like` | `HERO_LIB.has_modifier_like(pawn: PlayerPawn?, needle: string) -> boolean` | safe | True when any modifier name on the pawn contains the given substring. |
| `MOD_STATE.BLIND` | `.MOD_STATE.BLIND: integer` | safe | Live modifier-state bit for BLIND. |
| `MOD_STATE.DEAF` | `.MOD_STATE.DEAF: integer` | safe | Live modifier-state bit for DEAF. |
| `MOD_STATE.FORCE_ALERT_STATE` | `.MOD_STATE.FORCE_ALERT_STATE: integer` | safe | Live modifier-state bit for FORCE_ALERT_STATE. |
| `MOD_STATE.INVISIBLE_TO_ENEMY` | `.MOD_STATE.INVISIBLE_TO_ENEMY: integer` | safe | Live modifier-state bit for INVISIBLE_TO_ENEMY. |
| `MOD_STATE.MATERIAL_OVERRIDE` | `.MOD_STATE.MATERIAL_OVERRIDE: integer` | safe | Live modifier-state bit for MATERIAL_OVERRIDE. |
| `MOD_STATE.SILENCED` | `.MOD_STATE.SILENCED: integer` | safe | Live modifier-state bit for SILENCED. |
| `MOD_STATE.STATUS_IMMUNE` | `.MOD_STATE.STATUS_IMMUNE: integer` | safe | Live modifier-state bit for STATUS_IMMUNE. |
| `MOD_STATE.UNRESTRICTED_MOVEMENT` | `.MOD_STATE.UNRESTRICTED_MOVEMENT: integer` | safe | Live modifier-state bit for UNRESTRICTED_MOVEMENT. |
| `disable_squad` | `HERO_LIB.disable_squad(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISABLE_SQUAD modifier state. |
| `healing_disabled` | `HERO_LIB.healing_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HEALING_DISABLED modifier state. |
| `is_busy_with_action_bit` | `HERO_LIB.is_busy_with_action_bit(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the BUSY_WITH_ACTION modifier state. |
| `is_defused` | `HERO_LIB.is_defused(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DEFUSED modifier state. |
| `is_force_alert` | `HERO_LIB.is_force_alert(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the FORCE_ALERT_STATE modifier state. |
| `is_ignored_unit_filter` | `HERO_LIB.is_ignored_unit_filter(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IGNORED_BY_UNIT_FILTER modifier state. |
| `is_invisible_to_enemy` | `HERO_LIB.is_invisible_to_enemy(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the INVISIBLE_TO_ENEMY modifier state. |
| `is_movement_restricted` | `HERO_LIB.is_movement_restricted(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MOVEMENT_ABILITY_ACTIVATION_RESTRICTED modifier state. |
| `is_scoped` | `HERO_LIB.is_scoped(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SCOPED modifier state. |
| `is_slowed` | `HERO_LIB.is_slowed(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SLOWED modifier state. |
| `is_tech_untargetable_enemies` | `HERO_LIB.is_tech_untargetable_enemies(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the TECH_UNTARGETABLE_BY_ENEMIES modifier state. |
| `melee_attacks_only` | `HERO_LIB.melee_attacks_only(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MELEE_ATTACKS_ONLY modifier state. |
| `sprint_no_interrupt` | `HERO_LIB.sprint_no_interrupt(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SPRINT_NO_INTERRUPT modifier state. |
| `distance_pawns` | `HERO_LIB.distance_pawns(a: PlayerPawn, b: PlayerPawn) -> number` | safe | World-space 3D distance in units between two pawns' tick origins; 0 when either pawn is missing. |
| `is_enemy` | `HERO_LIB.is_enemy(pawn: PlayerPawn) -> boolean` | safe | True when the pawn's relation to the local pawn is opposed. |
| `missing_health` | `HERO_LIB.missing_health(pawn: PlayerPawn) -> integer` | safe | Max health minus current health; 0 when the pawn's facts are unavailable. |
| `pawn_origin` | `HERO_LIB.pawn_origin(pawn: PlayerPawn) -> Vector3\|nil` | safe | Pawn's current tick origin; nil when the pawn is missing. |
| `should_ignore_target_v2` | `HERO_LIB.should_ignore_target_v2(pawn: PlayerPawn?) -> boolean` | safe | True when combo targeting should skip the pawn (defaults to the local pawn when none is given). |
| `ally_hp_avg_percent` | `HERO_LIB.ally_hp_avg_percent() -> number` | safe | Average health fraction across living friendly pawns in the frame; 0 when there are none or the frame is unstable. |
| `enemies_alive` | `HERO_LIB.enemies_alive() -> table` | safe | Array of living enemy pawns from the current frame, capped at 32 entries. |
| `nearest_enemy_alive` | `HERO_LIB.nearest_enemy_alive() -> PlayerPawn\|nil` | safe | Living enemy pawn with the smallest frame distance to the local pawn; nil when none qualifies. |
| `clamp_to_cast_envelope` | `HERO_LIB.clamp_to_cast_envelope(from: Vector3, view_dir: Vector3, candidate: Vector3, range?: number) -> Vector3\|nil` | safe | Clamps the candidate point into the cast envelope defined by the from-point, view direction and range (defaults to 4000 units); nil when any input vector is missing. |
| `ease_step` | `HERO_LIB.ease_step(cur: number, target: number, dt?: number, factor?: number) -> number` | safe | Two-factor eased step from cur toward target over dt (default 0.016 s) with the given factor (default 1). |
| `pos_dot` | `HERO_LIB.pos_dot(a: Vector3, b: Vector3) -> number` | safe | Dot product of two Vector3 inputs; 0 when either vector can't be read. |
| `sanitize` | `HERO_LIB.sanitize(v: number, fallback?: number) -> number` | safe | Returns v when it is finite, otherwise the fallback (default 0). |
| `SLOT.ITEM_2` | `.SLOT.ITEM_2: integer` | safe | Slot index for the second active-item slot (ESlot_ActiveItem_2). |
| `ability_cooldown_remaining` | `HERO_LIB.ability_cooldown_remaining(ability_or_slot: Ability\|integer) -> number` | safe | Seconds of cooldown remaining on the ability (or ability resolved from local slot); 0 when ready or missing. |
| `can_activate_ability_check` | `HERO_LIB.can_activate_ability_check(ability_or_slot: Ability\|integer) -> boolean` | safe | True when the ability (or local slot) currently passes the engine's activation check. |
| `ability_cast_range` | `HERO_LIB.ability_cast_range(ability: Ability) -> number` | safe | Scaled AbilityCastRange property in units; 0 when the ability is missing. |
| `ability_is_targeted` | `HERO_LIB.ability_is_targeted(ability: Ability) -> boolean` | safe | True when the ability's vdata is resolved and the CITADEL_ABILITY_BEHAVIOR_NO_TARGET behavior bit is not set; false while unknown. |
| `ability_info` | `HERO_LIB.ability_info(ability_or_slot: Ability\|integer) -> table` | safe | Snapshot table for the ability with fields index, cd_end, cast_start, post_cast_end, proj_speed, charges, in_cast_delay, channeling, cd_remaining, ready; empty table when the ability is missing. |
| `enabled_state_bits` | `HERO_LIB.enabled_state_bits(pawn: PlayerPawn) -> table` | safe | Array of static state-bit indices (word*32+bit) currently enabled on the pawn's state mask. |
| `get_neutral_trooper_type` | `HERO_LIB.get_neutral_trooper_type(ent: Entity) -> integer\|nil` | safe | ENeutralNPCType value read from the NPC's TrooperNeutralVData; nil when the entity isn't a jungle-camp neutral or the field can't be read on the game thread. |
| `ENUM_PPS_INFO_FROM.GUN` | `.ENUM_PPS_INFO_FROM.GUN: integer` | safe | Projectile-prediction source selector that reads muzzle/speed from the gun eye position. |
| `elapsed_ms` | `HERO_LIB.elapsed_ms() -> number` | safe | High-resolution tick counter converted to milliseconds (100-ns ticks / 10000). |
| `is_invulnerable` | `HERO_LIB.is_invulnerable(pawn: PlayerPawn) -> boolean` | safe | True when the pawn has the INVULNERABLE or NO_INCOMING_DAMAGE modifier state on a stable frame. |
| `modifier_is_buff` | `HERO_LIB.modifier_is_buff(pawn: PlayerPawn, s: string) -> boolean` | safe | True when the named modifier is resolved on the pawn and its vdata debuff type classifies it as a buff (not DEBUFF_YES, and not ENEMY_TEAM_ONLY on an opposing team). |
| `projectile_flight_time` | `HERO_LIB.projectile_flight_time(origin: Vector3, target: Vector3, speed?: number) -> number` | safe | Travel time in seconds from origin to target at the given projectile speed; 0 when either vector cannot be read. |
| `INNATE.JUMP` | `.INNATE.JUMP: integer` | safe | EInnateAction id for the Jump innate action. |
| `bullet_speed` | `HERO_LIB.bullet_speed() -> number` | safe | Local controller's actual projectile speed from WeaponSpeed; 0 when there is no local controller. |
| `health_pct` | `HERO_LIB.health_pct() -> number` | safe | Local pawn's current-to-max health fraction in [0,1]; 0 when the local pawn is missing. |
| `is_ivy` | `HERO_LIB.is_ivy() -> boolean` | safe | True when the local hero id resolves to Ivy. |
| `is_vindicta` | `HERO_LIB.is_vindicta() -> boolean` | safe | True when the local hero id resolves to Vindicta. |
| `local_view_dir_helper` | `HERO_LIB.local_view_dir_helper() -> Vector3` | safe | Local player's view direction, falling back to {1,0,0} when the local frame is invalid. |
| `weapon_stats` | `HERO_LIB.weapon_stats() -> table` | safe | Table with the local weapon's speed, gravity, radius, world_radius and lifetime from WeaponSpeed; empty table when there is no local controller. |
| `iter_active_modifiers` | `HERO_LIB.iter_active_modifiers(pawn: PlayerPawn) -> table` | safe | Array of modifier info tables for the pawn's non-disabled modifiers; empty table when the pawn is missing. |
| `MOD_STATE.BURNING` | `.MOD_STATE.BURNING: integer` | safe | Live modifier-state bit for BURNING. |
| `MOD_STATE.DEFUSED` | `.MOD_STATE.DEFUSED: integer` | safe | Live modifier-state bit for DEFUSED. |
| `MOD_STATE.FROZEN` | `.MOD_STATE.FROZEN: integer` | safe | Live modifier-state bit for FROZEN. |
| `MOD_STATE.INVISIBLE_TO_ENEMY_CAST` | `.MOD_STATE.INVISIBLE_TO_ENEMY_CAST: integer` | safe | Live modifier-state bit for INVISIBLE_TO_ENEMY_CAST. |
| `MOD_STATE.MELEE_ATTACKS_ONLY` | `.MOD_STATE.MELEE_ATTACKS_ONLY: integer` | safe | Live modifier-state bit for MELEE_ATTACKS_ONLY. |
| `MOD_STATE.SILENCED_HIDDEN` | `.MOD_STATE.SILENCED_HIDDEN: integer` | safe | Live modifier-state bit for SILENCED_HIDDEN. |
| `MOD_STATE.STUNNED` | `.MOD_STATE.STUNNED: integer` | safe | Live modifier-state bit for STUNNED. |
| `MOD_STATE.UNSTOPPABLE` | `.MOD_STATE.UNSTOPPABLE: integer` | safe | Live modifier-state bit for UNSTOPPABLE. |
| `entering_vehicle` | `HERO_LIB.entering_vehicle(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the ENTERING_VEHICLE modifier state. |
| `health_external_regen_disabled` | `HERO_LIB.health_external_regen_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HEALTH_EXTERNAL_REGEN_DISABLED modifier state. |
| `is_busy_with_action_non_item` | `HERO_LIB.is_busy_with_action_non_item(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the BUSY_WITH_ACTION_NON_ITEM modifier state. |
| `is_disable_gravity` | `HERO_LIB.is_disable_gravity(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISABLE_GRAVITY modifier state. |
| `is_frozen` | `HERO_LIB.is_frozen(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the FROZEN modifier state. |
| `is_immobilized` | `HERO_LIB.is_immobilized(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IMMOBILIZED modifier state. |
| `is_invisible_to_enemy_on_cast` | `HERO_LIB.is_invisible_to_enemy_on_cast(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the INVISIBLE_TO_ENEMY_CAST modifier state. |
| `is_muted` | `HERO_LIB.is_muted(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MUTED modifier state. |
| `is_shooting_disabled` | `HERO_LIB.is_shooting_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SHOOTING_DISABLED modifier state. |
| `is_sprint_disabled` | `HERO_LIB.is_sprint_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SPRINT_DISABLED modifier state. |
| `is_tech_untargetable_teammates` | `HERO_LIB.is_tech_untargetable_teammates(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the TECH_UNTARGETABLE_BY_TEAMMATES modifier state. |
| `no_incoming_damage` | `HERO_LIB.no_incoming_damage(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the NO_INCOMING_DAMAGE modifier state. |
| `visible_to_enemy` | `HERO_LIB.visible_to_enemy(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the VISIBLE_TO_ENEMY modifier state. |
| `distance_pawns_m` | `HERO_LIB.distance_pawns_m(a: PlayerPawn, b: PlayerPawn) -> number` | safe | Distance in meters between the two pawns' tick origins; 0 when either argument fails to resolve. |
| `is_enemy_of` | `HERO_LIB.is_enemy_of(a: PlayerPawn, b: PlayerPawn) -> boolean` | safe | True when both pawns resolve to facts and their team numbers differ. |
| `overkill` | `HERO_LIB.overkill(pawn: PlayerPawn, dmg?: number) -> integer` | safe | max(0, dmg - current health) in integer HP; 0 when the pawn's facts can't be read. |
| `pawn_team` | `HERO_LIB.pawn_team(pawn: PlayerPawn) -> integer` | safe | Pawn's team number from its facts; -1 when facts aren't available. |
| `speed` | `HERO_LIB.speed(pawn: PlayerPawn) -> number` | safe | Magnitude of the pawn's 3D velocity in units/s; 0 when facts aren't available. |
| `angle_to_target` | `HERO_LIB.angle_to_target(pawn: PlayerPawn) -> number` | safe | Angle in degrees between the local view direction and the target pawn's origin; 999 when the pawn or local view is unavailable. |
| `enemy_hp_sum` | `HERO_LIB.enemy_hp_sum() -> integer` | safe | Sum of the health values of all enemy pawns in the current frame scan; 0 when the local player isn't valid or the frame goes unstable. |
| `nearest_soul` | `HERO_LIB.nearest_soul() -> Vector3\|nil` | safe | Origin of the nearest soul (ItemXP role) entity to the local pawn; nil when none is found or there is no local pawn. |
| `cross` | `HERO_LIB.cross(a: Vector3, b: Vector3) -> Vector3` | safe | Vector cross product of a and b (zeros used for missing args). |
| `forward_to_yaw` | `HERO_LIB.forward_to_yaw(forward: Vector3) -> number` | safe | Yaw in degrees from a forward vector via atan2(y, x); 0 when the vector has no XY component. |
| `pos_from` | `HERO_LIB.pos_from(x?: number, y?: number, z?: number) -> Vector3` | safe | Builds a Vector3 from the three component arguments, each defaulting to 0. |
| `sign` | `HERO_LIB.sign(n?: number) -> integer` | safe | Returns 1 for positive n, -1 for negative, 0 for zero (default 0). |
| `SLOT.ITEM_3` | `.SLOT.ITEM_3: integer` | safe | Ability slot index of the third active item. |
| `ability_health` | `HERO_LIB.ability_health(ability: Ability\|integer) -> integer` | safe | Current health of the ability (useful for ones that expose HP, e.g. deployables); 0 when missing. |
| `has_ability_slot` | `HERO_LIB.has_ability_slot(slotOrName: integer\|string, pawn?: PlayerPawn) -> boolean` | safe | True when the pawn has an ability either in the given slot (integer) or whose name matches (string); defaults to the local pawn. |
| `ability_cast_refresh_time` | `HERO_LIB.ability_cast_refresh_time(ability: Ability) -> number` | safe | Scaled AbilityCooldown property — base refresh/cooldown time between casts; 0 when missing. |
| `ability_is_ultimate` | `HERO_LIB.ability_is_ultimate(ability: Ability) -> boolean` | safe | True when the ability occupies the signature-4 (ultimate) slot. |
| `ability_post_cast_end` | `HERO_LIB.ability_post_cast_end(ability: Ability\|integer) -> number` | safe | Raw m_flPostCastDelayEndTime of the ability; 0 when missing. |
| `is_dashing` | `HERO_LIB.is_dashing(pawn?: PlayerPawn) -> boolean` | safe | True while the pawn is ground- or air-dashing; the local pawn uses the live action-state locomotion bits, others fall back to the modifier mask. |
| `get_npc_kind` | `HERO_LIB.get_npc_kind(ent: Entity) -> string\|nil` | safe | Returns a short NPC kind string ("patron", "trooper", "guardian", "neutral", "walker", "shrine", "midboss", "base_guardian") for the entity, or nil if the frame is unstable or the entity is not a known NPC. |
| `ENUM_PPS_INFO_FROM.PROJECTILE` | `.ENUM_PPS_INFO_FROM.PROJECTILE: integer` | safe | Selector value passed to projectile predictors to source speed/gravity from the ability's projectile data. |
| `force_gc` | `HERO_LIB.force_gc() -> integer` | safe | Runs a full Lua garbage collection cycle and returns the number of bytes freed. |
| `is_tech_invulnerable` | `HERO_LIB.is_tech_invulnerable(pawn?: PlayerPawn) -> boolean` | safe | True when the pawn has either TECH_INVULNERABLE or TECH_DAMAGE_INVULNERABLE enabled on a stable frame. |
| `modifier_state_mask_for` | `HERO_LIB.modifier_state_mask_for(pawn: PlayerPawn, name: string, word?: integer) -> integer` | safe | Reads the given 32-bit word of the named modifier's state-mask array out of its VData; returns 0 when the modifier, pawn, offset or word index is unresolved. |
| `safe_call` | `HERO_LIB.safe_call(f: function, ...: any) -> boolean, ...` | safe | Protected pcall with a traceback error handler: returns (true, results...) on success or (false, message) on error; (false, message) when the first argument is not a function. |
| `INNATE.LIGHT_MELEE` | `.INNATE.LIGHT_MELEE: integer` | safe | Innate-action index for the light-melee action. |
| `dt` | `HERO_LIB.dt() -> number` | safe | Current server tick interval, in seconds. |
| `hero_id` | `HERO_LIB.hero_id() -> integer` | safe | Local controller's hero id, or 0 when there is no controller. |
| `is_lash` | `HERO_LIB.is_lash() -> boolean` | safe | True when the local hero is Lash. |
| `is_viscous` | `HERO_LIB.is_viscous() -> boolean` | safe | True when the local hero is Viscous. |
| `mana` | `HERO_LIB.mana() -> number\|nil` | safe | Current value of the local pawn's ability-resource pool; nil when the pawn, component or field offset is unresolved. |
| `count_modifier_like` | `HERO_LIB.count_modifier_like(pawn: PlayerPawn, needle: string) -> integer` | safe | Count of modifiers on the pawn whose name contains the substring; 0 when the pawn or needle is missing. |
| `max_modifier_remaining` | `HERO_LIB.max_modifier_remaining(pawn: PlayerPawn, names: string[]) -> number` | safe | Longest remaining time among the listed modifiers on the pawn; -1 if any matching modifier has no duration (infinite), 0 when none match. |
| `MOD_STATE.BUSY_WITH_ACTION` | `.MOD_STATE.BUSY_WITH_ACTION: integer` | safe | Live modifier-state bit for BUSY_WITH_ACTION. |
| `MOD_STATE.DISABLE_GRAVITY` | `.MOD_STATE.DISABLE_GRAVITY: integer` | safe | Live modifier-state bit for DISABLE_GRAVITY. |
| `MOD_STATE.GROUND_DASHING` | `.MOD_STATE.GROUND_DASHING: integer` | safe | Live modifier-state bit for GROUND_DASHING. |
| `MOD_STATE.INVULNERABLE` | `.MOD_STATE.INVULNERABLE: integer` | safe | Live modifier-state bit for INVULNERABLE. |
| `MOD_STATE.MOVEMENT_ABILITY_RESTRICTED` | `.MOD_STATE.MOVEMENT_ABILITY_RESTRICTED: integer` | safe | Live modifier-state bit for MOVEMENT_ABILITY_ACTIVATION_RESTRICTED. |
| `MOD_STATE.SILENCE_MOVEMENT` | `.MOD_STATE.SILENCE_MOVEMENT: integer` | safe | Live modifier-state bit for SILENCE_MOVEMENT_ABILITES. |
| `MOD_STATE.TECH_DAMAGE_INVULNERABLE` | `.MOD_STATE.TECH_DAMAGE_INVULNERABLE: integer` | safe | Live modifier-state bit for TECH_DAMAGE_INVULNERABLE. |
| `MOD_STATE.UNTARGETABLE` | `.MOD_STATE.UNTARGETABLE: integer` | safe | Live modifier-state bit for TECH_UNTARGETABLE_BY_ENEMIES (used as the untargetable sentinel). |
| `exiting_vehicle` | `HERO_LIB.exiting_vehicle(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the EXITING_VEHICLE modifier state. |
| `health_regen_disabled` | `HERO_LIB.health_regen_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HEALTH_REGEN_DISABLED modifier state. |
| `is_busy_with_action_state` | `HERO_LIB.is_busy_with_action_state(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the BUSY_WITH_ACTION modifier state. |
| `is_disable_sensing` | `HERO_LIB.is_disable_sensing(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISABLE_SENSING modifier state. |
| `is_ground_dashing` | `HERO_LIB.is_ground_dashing(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the GROUND_DASHING modifier state. |
| `is_in_combat` | `HERO_LIB.is_in_combat(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IN_COMBAT modifier state. |
| `is_items_disabled` | `HERO_LIB.is_items_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the ITEMS_DISABLED modifier state. |
| `is_npc_targetable_while_inv` | `HERO_LIB.is_npc_targetable_while_inv(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the NPC_TARGETABLE_WHILE_INVULNERABLE modifier state. |
| `is_shooting_forced_on` | `HERO_LIB.is_shooting_forced_on(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SHOOTING_FORCED_ON modifier state. |
| `is_sprint_no_interrupt` | `HERO_LIB.is_sprint_no_interrupt(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SPRINT_NO_INTERRUPT modifier state. |
| `is_unkillable` | `HERO_LIB.is_unkillable(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the UNKILLABLE modifier state. |
| `no_outgoing_damage` | `HERO_LIB.no_outgoing_damage(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the NO_OUTGOING_DAMAGE modifier state. |
| `TEAM.AMBER` | `.TEAM.AMBER: integer` | safe | Team id of the Amber side. |
| `dmg_to_kill` | `HERO_LIB.dmg_to_kill(pawn: PlayerPawn) -> integer` | safe | Current HP of the pawn when it is alive and above 0, else 0 — the damage needed to kill it. |
| `is_hard_ccd` | `HERO_LIB.is_hard_ccd(pawn?: PlayerPawn) -> boolean` | safe | Delegates to the native hard-CC check for the pawn (or local pawn when omitted). |
| `pawn_flags` | `HERO_LIB.pawn_flags(pawn: PlayerPawn) -> integer` | safe | The pawn's entity flags bitfield from the frame facts; 0 when the pawn does not resolve. |
| `pawn_valid` | `HERO_LIB.pawn_valid(pawn: PlayerPawn) -> boolean` | safe | True when the pawn resolves to a frame record and is alive with health > 0. |
| `speed_2d` | `HERO_LIB.speed_2d(pawn?: PlayerPawn) -> number` | safe | Horizontal (XY) length of the pawn's velocity vector; 0 when facts do not resolve. |
| `best_target_in_cone` | `HERO_LIB.best_target_in_cone(coneDeg?: number, radius?: number) -> PlayerPawn\|nil` | safe | Alive enemy pawn with the smallest view angle inside the cone (default 30°) and radius (default 4000 units); nil if none qualify. |
| `enemy_lowest_hp_in_radius` | `HERO_LIB.enemy_lowest_hp_in_radius(center?: Vector3, radius?: number) -> PlayerPawn\|nil` | safe | Alive enemy with the lowest HP whose origin lies inside the radius (default 1000 units) around the center (defaults to the local pawn's position); nil when there is no local player or no match. |
| `pawn_within_cone` | `HERO_LIB.pawn_within_cone(pawn: PlayerPawn, coneDeg?: number) -> boolean` | safe | True when the pawn's origin lies within the given cone (default 30°) of the local view direction. |
| `dist_2d` | `HERO_LIB.dist_2d(a: Vector3, b: Vector3) -> number` | safe | Horizontal (XY) distance between two points; 0 when either argument fails to read as a Vector3. |
| `fov_between` | `HERO_LIB.fov_between(eye: Vector3, dir: Vector3, target: Vector3) -> number` | safe | Angle in degrees between the view direction at eye and the vector toward target; 0 when any argument fails to read. |
| `pos_length` | `HERO_LIB.pos_length(v: Vector3) -> number` | safe | 3D length (magnitude) of the vector; 0 when the argument fails to read. |
| `within_cone` | `HERO_LIB.within_cone(eye: Vector3, dir: Vector3, target: Vector3, coneDeg?: number) -> boolean` | safe | True when the target point lies within the given cone (default 30°) around dir anchored at eye. |
| `SLOT.ITEM_4` | `.SLOT.ITEM_4: integer` | safe | Slot index of the fourth active item (ESlot_ActiveItem_4). |
| `ability_in_cast_delay` | `HERO_LIB.ability_in_cast_delay(ability: Ability\|integer) -> boolean` | safe | Raw read of the ability's m_bInCastDelay netvar; false when the ability is missing. |
| `is_ability_channeling` | `HERO_LIB.is_ability_channeling(ability: Ability\|integer) -> boolean` | safe | True when the ability is currently channeling, as reported by the combo helper. |
| `ability_cast_time` | `HERO_LIB.ability_cast_time(ability: Ability) -> number` | safe | Computed cast-delay in seconds for the ability; 0 when the ability is missing. |
| `ability_max_charges` | `HERO_LIB.ability_max_charges(ability: Ability) -> integer` | safe | Scaled AbilityCharges property rounded to an integer; 0 when the ability is missing. |
| `ability_raw_projectile_speed` | `HERO_LIB.ability_raw_projectile_speed(ability: Ability\|integer) -> number` | safe | Raw ability projectile speed from GetProjectileSpeed; 0 when the ability is missing. |
| `pawn_status_flags` | `HERO_LIB.pawn_status_flags(pawn: PlayerPawn?) -> table` | safe | Table of named modifier-state booleans (stunned, silenced, rooted, disarmed, slowed, sprinting, sliding, air_dashing, ground_dashing, unstoppable, invulnerable, burning, scoped, flying, zipline, obscured, invisible_to_enemy); empty table if the pawn's state mask is unreadable. |
| `get_trooper_type` | `HERO_LIB.get_trooper_type(ent: Entity) -> integer\|nil` | safe | TrooperType_t enum value read from a trooper NPC's vdata on the game thread; nil for non-troopers or when the field cannot be resolved. |
| `ability_is_passive` | `HERO_LIB.ability_is_passive(ability: Ability?) -> boolean` | safe | Compatibility stub that always returns false. |
| `get_aimbot_target` | `HERO_LIB.get_aimbot_target() -> Vector3\|nil` | safe | Last position passed to set_aimbot_target, or nil if no manual aimbot target is active. |
| `lag_comp.get` | `HERO_LIB.lag_comp.get(pawn: PlayerPawn, offset: integer?) -> table\|nil` | safe | Backtrack sample for the pawn as {origin, velocity, eye_angles, simtime}; with a positive tick offset returns the record at (current tick - offset), otherwise the best record. Returns nil off the game thread, for an invalid pawn, or when no usable record exists. |
| `no_obs_to_pos_v2` | `HERO_LIB.no_obs_to_pos_v2(from: Vector3, to: Vector3) -> boolean` | safe | True when combo::no_obs_to_pos reports an unobstructed line between the two points; true by default when the arguments are not readable vectors. |
| `set_aimbot_target` | `HERO_LIB.set_aimbot_target(pos: Vector3) -> boolean` | safe | Pins the PSilent manual aim target to the given world position for the owning script; returns false if the vector cannot be read. |
| `INNATE.MANTLE` | `.INNATE.MANTLE: integer` | safe | Innate-action index for Mantle, as used by innate_ready / innate_press. |
| `eye_forward` | `HERO_LIB.eye_forward() -> Vector3\|nil` | safe | Local player's eye forward (view direction); nil when the local player is invalid. |
| `is_abrams` | `HERO_LIB.is_abrams() -> boolean` | safe | True when the local hero is Abrams. |
| `is_local_hero` | `HERO_LIB.is_local_hero(hero_id: integer) -> boolean` | safe | True when the given hero id matches the local controller's hero id. |
| `is_warden` | `HERO_LIB.is_warden() -> boolean` | safe | True when the local hero is Warden. |
| `match_time` | `HERO_LIB.match_time() -> number` | safe | Current match time in seconds from combo::get_match_time. |
| `count_modifiers` | `HERO_LIB.count_modifiers(pawn: PlayerPawn?) -> integer` | safe | Number of active (non-disabled) modifiers on the pawn; 0 when the pawn is missing. |
| `modifier_duration` | `HERO_LIB.modifier_duration(pawn: PlayerPawn?, name: string) -> number` | safe | Duration of the named modifier on the pawn: the stored duration if positive, -1 for an infinite modifier (duration <= 0), 0 when the modifier is not present. |
| `MOD_STATE.BUSY_WITH_ACTION_NON_ITEM` | `.MOD_STATE.BUSY_WITH_ACTION_NON_ITEM: integer` | safe | Live modifier-state bit for BUSY_WITH_ACTION_NON_ITEM. |
| `MOD_STATE.DISABLE_SENSING` | `.MOD_STATE.DISABLE_SENSING: integer` | safe | Live modifier-state bit for DISABLE_SENSING. |
| `MOD_STATE.HEALING_DISABLED` | `.MOD_STATE.HEALING_DISABLED: integer` | safe | Live modifier-state bit for HEALING_DISABLED. |
| `MOD_STATE.IN_ENEMY_BASE` | `.MOD_STATE.IN_ENEMY_BASE: integer` | safe | Live modifier-state bit for IN_ENEMY_BASE. |
| `MOD_STATE.MUTED` | `.MOD_STATE.MUTED: integer` | safe | Live modifier-state bit for MUTED. |
| `MOD_STATE.SLIDING` | `.MOD_STATE.SLIDING: integer` | safe | Live modifier-state bit for SLIDING. |
| `MOD_STATE.TECH_INVULNERABLE` | `.MOD_STATE.TECH_INVULNERABLE: integer` | safe | Live modifier-state bit for TECH_INVULNERABLE. |
| `MOD_STATE.VISIBLE_TO_ENEMY` | `.MOD_STATE.VISIBLE_TO_ENEMY: integer` | safe | Live modifier-state bit for VISIBLE_TO_ENEMY. |
| `force_alert_state` | `HERO_LIB.force_alert_state(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the FORCE_ALERT_STATE modifier state. |
| `ignores_bullets` | `HERO_LIB.ignores_bullets(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IGNORE_BULLETS modifier state. |
| `is_charging` | `HERO_LIB.is_charging(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the CHARGING modifier state. |
| `is_disable_squad` | `HERO_LIB.is_disable_squad(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISABLE_SQUAD modifier state. |
| `is_healing_disabled` | `HERO_LIB.is_healing_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HEALING_DISABLED modifier state. |
| `is_in_enemy_base` | `HERO_LIB.is_in_enemy_base(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IN_ENEMY_BASE modifier state. |
| `is_jump_disabled` | `HERO_LIB.is_jump_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the JUMP_DISABLED modifier state. |
| `is_npc_targetable_while_invulnerable` | `HERO_LIB.is_npc_targetable_while_invulnerable(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the NPC_TARGETABLE_WHILE_INVULNERABLE modifier state. |
| `is_silence_movement` | `HERO_LIB.is_silence_movement(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SILENCE_MOVEMENT_ABILITES modifier state. |
| `is_sprinting` | `HERO_LIB.is_sprinting(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SPRINTING modifier state. |
| `is_unrestricted_movement` | `HERO_LIB.is_unrestricted_movement(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the UNRESTRICTED_MOVEMENT modifier state. |
| `sensing_disabled` | `HERO_LIB.sensing_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISABLE_SENSING modifier state. |
| `TEAM.NEUTRAL` | `.TEAM.NEUTRAL: integer` | safe | Team id for neutral units. |
| `get_team` | `HERO_LIB.get_team(pawn: PlayerPawn?) -> integer` | safe | Team id of the pawn (local pawn when omitted) from combo::get_team. |
| `is_lethal_dmg` | `HERO_LIB.is_lethal_dmg(pawn: PlayerPawn?, damage: number?) -> boolean` | safe | True when the pawn is alive and the given damage amount is at least its current health. |
| `pawn_health_pct` | `HERO_LIB.pawn_health_pct(pawn: PlayerPawn) -> number` | safe | Pawn's health as a 0..1 fraction of max health; 0 when the pawn is missing or has no max health. |
| `pawn_velocity` | `HERO_LIB.pawn_velocity(pawn: PlayerPawn) -> Vector3\|nil` | safe | Pawn's velocity vector from the entity frame; nil when the pawn's facts are unreadable. |
| `target_hp_percent` | `HERO_LIB.target_hp_percent(pawn: PlayerPawn) -> number` | safe | Pawn's health as a 0..1 fraction of max health; 0 when the pawn is missing or has no max health. |
| `count_alive_allies` | `HERO_LIB.count_alive_allies() -> integer` | safe | Number of living allied player pawns in the entity frame; 0 when the local player is invalid. |
| `iter_pawns` | `HERO_LIB.iter_pawns() -> table` | safe | Array of PlayerPawn light-userdata for every pawn in the entity frame, capped at 64. |
| `pick_weighted_target` | `HERO_LIB.pick_weighted_target(cone_deg: number?, radius: number?, dist_weight: number?, angle_weight: number?) -> PlayerPawn\|nil` | safe | Enemy within the given view cone (default 30 deg) and radius (default 4000) that minimises angle * angle_weight + (dist / radius) * dist_weight; nil when none qualify. Defaults for both weights are 1. |
| `dist_meters` | `HERO_LIB.dist_meters(a: PlayerPawn\|Vector3, b: PlayerPawn\|Vector3) -> number` | safe | Distance between two points or two pawns' tick origins, in meters; 0 when the arguments are unreadable. |
| `length_of` | `HERO_LIB.length_of(v: Vector3) -> number` | safe | 3D length of the vector; 0 when the argument is not a readable Vector3. |
| `pos_length_2d` | `HERO_LIB.pos_length_2d(v: Vector3) -> number` | safe | XY length of the vector (ignoring z); 0 when the argument is not a readable Vector3. |
| `within_radius` | `HERO_LIB.within_radius(a: Vector3, b: Vector3, radius: number?) -> boolean` | safe | True when the distance in units between the two points is at most radius (default 0); false if either argument is not a readable Vector3. |
| `SLOT.ULTIMATE` | `.SLOT.ULTIMATE: integer` | safe | Ability-slot id for the signature-4 ultimate. |
| `ability_in_cast_delay_raw` | `HERO_LIB.ability_in_cast_delay_raw(ability: Ability\|integer) -> boolean` | safe | Raw `m_bInCastDelay` flag on the ability; false when nil. |
| `item_cd_by_slot` | `HERO_LIB.item_cd_by_slot(ability: Ability\|integer) -> number` | safe | Cooldown remaining in seconds for the ability or slot (same resolver as `ability_cd_remaining`). |
| `ability_channel_time` | `HERO_LIB.ability_channel_time(ability: Ability) -> number` | safe | Scaled `AbilityChannelTime` property in seconds; 0 when the ability is nil. |
| `ability_projectile_gravity` | `HERO_LIB.ability_projectile_gravity(ability: Ability) -> number` | safe | Gravity for the ability's projectile from the throwable resolver; 0 when nil or when no projectile info resolves. |
| `can_cast_abilities` | `HERO_LIB.can_cast_abilities(pawn: PlayerPawn?) -> boolean` | safe | True when the pawn (or local pawn, if omitted) is currently permitted to cast abilities. |
| `QUICKCAST_MODE.CONFIRM` | `.QUICKCAST_MODE.CONFIRM: integer` | safe | Quickcast-mode id for press-and-confirm casts. |
| `is_hero_pawn` | `HERO_LIB.is_hero_pawn(entity: Entity) -> boolean` | safe | True when the entity resolves to a frame row with role PlayerPawn. |
| `ability_is_toggle` | `HERO_LIB.ability_is_toggle() -> boolean` | safe | Compatibility stub; always returns false. |
| `get_disable_remaining` | `HERO_LIB.get_disable_remaining(pawn: PlayerPawn?, enabled: boolean?) -> number\|nil` | safe | Longest remaining seconds across hard-disable modifiers (stun, immobilize, movement-disabled, sleep, dreamweaver-sleep, freeze); 0 when the second arg is `false`, nil when the pawn is missing or the mask can't resolve off-game-thread. |
| `mark_fired` | `HERO_LIB.mark_fired(tag: string?)` | safe | Marks the string tag as fired within the current combo window; later observed by `fired_this_combo`. |
| `no_obs_to_target_v2` | `HERO_LIB.no_obs_to_target_v2(pawn: PlayerPawn) -> boolean` | safe | Combo-helper line-of-sight check: true when `::av::combo::no_obs_to_target` reports no obstruction to the pawn. |
| `set_draw_target` | `HERO_LIB.set_draw_target(slot: integer, index: integer?, r: number?, g: number?, b: number?, a: number?) -> nil` | safe | Publishes the kill-indicator draw target for the slot: entity index (nil or negative clears it) and optional r,g,b,a tint in [0,1] packed as RGBA8. |
| `INNATE.PARRY` | `.INNATE.PARRY: integer` | safe | Innate-action id for the Parry input. |
| `eye_pos_view` | `HERO_LIB.eye_pos_view() -> Vector3\|nil` | safe | Camera eye position from the local-view snapshot; nil when the local player is unresolved. |
| `is_bebop` | `HERO_LIB.is_bebop() -> boolean` | safe | True when the local hero is Bebop. |
| `is_mcginnis` | `HERO_LIB.is_mcginnis() -> boolean` | safe | True when the local hero is McGinnis. |
| `is_wraith` | `HERO_LIB.is_wraith() -> boolean` | safe | True when the local hero is Wraith. |
| `max_health` | `HERO_LIB.max_health() -> integer` | safe | Local pawn's maximum health; 0 when the pawn or its facts are unavailable. |
| `get_all_modifiers` | `HERO_LIB.get_all_modifiers(pawn: PlayerPawn?) -> table` | safe | Array of per-modifier records (name, stack, buildup, duration, remaining, caster_index, ability_index, start_time, id, team, disabled, in_aura_range) for every modifier on the pawn; empty table when the pawn is missing. |
| `modifier_names` | `HERO_LIB.modifier_names(pawn: PlayerPawn?) -> table` | safe | Array of the pawn's modifier name strings; empty table when the pawn is missing. |
| `MOD_STATE.CHARGING` | `.MOD_STATE.CHARGING: integer` | safe | Live modifier-state bit for CHARGING. |
| `MOD_STATE.DISABLE_SQUAD` | `.MOD_STATE.DISABLE_SQUAD: integer` | safe | Live modifier-state bit for DISABLE_SQUAD. |
| `MOD_STATE.HEALTH_EXTERNAL_REGEN_DISABLED` | `.MOD_STATE.HEALTH_EXTERNAL_REGEN_DISABLED: integer` | safe | Live modifier-state bit for HEALTH_EXTERNAL_REGEN_DISABLED. |
| `MOD_STATE.IN_FOUNTAIN` | `.MOD_STATE.IN_FOUNTAIN: integer` | safe | Live modifier-state bit for IN_FOUNTAIN. |
| `MOD_STATE.NPC_TARGETABLE_WHILE_INVUL` | `.MOD_STATE.NPC_TARGETABLE_WHILE_INVUL: integer` | safe | Live modifier-state bit for NPC_TARGETABLE_WHILE_INVULNERABLE. |
| `MOD_STATE.SLIDING_SLOW_GETUP` | `.MOD_STATE.SLIDING_SLOW_GETUP: integer` | safe | Live modifier-state bit for SLIDING_SLOW_GETUP. |
| `MOD_STATE.TECH_UNTARGETABLE_BY_ENEMIES` | `.MOD_STATE.TECH_UNTARGETABLE_BY_ENEMIES: integer` | safe | Live modifier-state bit for TECH_UNTARGETABLE_BY_ENEMIES. |
| `MOD_STATE.WALLSLIDE` | `.MOD_STATE.WALLSLIDE: integer` | safe | Live modifier-state bit for WALLSLIDE. |
| `has_additional_air_moves` | `HERO_LIB.has_additional_air_moves(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the ADDITIONAL_AIR_MOVES modifier state. |
| `ignores_melee` | `HERO_LIB.ignores_melee(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IGNORE_MELEE modifier state. |
| `is_combat_abilities_disabled` | `HERO_LIB.is_combat_abilities_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the COMBAT_ABILITIES_DISABLED modifier state. |
| `is_disabled` | `HERO_LIB.is_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn is stunned, frozen, silenced, or disarmed (any of those static state bits). |
| `is_hp_ext_regen_disabled` | `HERO_LIB.is_hp_ext_regen_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HEALTH_EXTERNAL_REGEN_DISABLED modifier state. |
| `is_in_fountain` | `HERO_LIB.is_in_fountain(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IN_FOUNTAIN modifier state. |
| `is_knockdown_immune` | `HERO_LIB.is_knockdown_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the KNOCKDOWN_IMMUNE modifier state. |
| `is_obscured` | `HERO_LIB.is_obscured(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the OBSCURED modifier state. |
| `is_silenced` | `HERO_LIB.is_silenced(pawn: PlayerPawn) -> boolean` | safe | True when the pawn has either the SILENCED or SILENCED_HIDDEN static state bit set. |
| `is_state_enabled` | `HERO_LIB.is_state_enabled(pawn: PlayerPawn?, bit: integer?) -> boolean` | safe | True when the pawn's live state mask has the given MOD_STATE bit set. |
| `is_unstoppable` | `HERO_LIB.is_unstoppable(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the UNSTOPPABLE modifier state. |
| `shooting_disabled` | `HERO_LIB.shooting_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SHOOTING_DISABLED modifier state. |
| `TEAM.SAPPHIRE` | `.TEAM.SAPPHIRE: integer` | safe | Team id for the Sapphire side. |
| `hp_after_dmg` | `HERO_LIB.hp_after_dmg(pawn: PlayerPawn, damage: number?) -> integer` | safe | Pawn's current health minus `damage` (truncated to int), clamped to 0; 0 when the pawn's facts are unavailable. |
| `is_local` | `HERO_LIB.is_local(pawn: PlayerPawn) -> boolean` | safe | True when the pawn pointer equals the local pawn. |
| `pawn_health_percent` | `HERO_LIB.pawn_health_percent(pawn: PlayerPawn) -> number` | safe | Pawn's current health as a fraction of its max in [0,1]; 0 when the pawn or its facts are unavailable. |
| `predict_pawn_position` | `HERO_LIB.predict_pawn_position(pawn: PlayerPawn?, seconds: number?) -> Vector3` | safe | Pawn origin plus velocity * seconds; zero vector when the pawn is missing. |
| `team_of` | `HERO_LIB.team_of(pawn: PlayerPawn) -> integer` | safe | Pawn's team id from its facts; 0 when unavailable. |
| `count_alive_enemies` | `HERO_LIB.count_alive_enemies() -> integer` | safe | Count of alive enemy player pawns on the current frame. |
| `lowest_hp_enemy` | `HERO_LIB.lowest_hp_enemy() -> PlayerPawn\|nil` | safe | Alive enemy pawn with the lowest health; nil when none. |
| `angle_between` | `HERO_LIB.angle_between(a: Vector3, b: Vector3) -> number` | safe | Angle in degrees between two direction vectors; missing arguments are treated as the zero vector. |
| `dist_sq` | `HERO_LIB.dist_sq(a: Vector3, b: Vector3) -> number` | safe | Squared distance between two Vec3 points; 0 when either argument is missing. |
| `lerp` | `HERO_LIB.lerp(a: number?, b: number?, t: number?) -> number` | safe | Linear interpolation between a and b by t clamped to [0,1]. |
| `pos_lerp` | `HERO_LIB.pos_lerp(a: Vector3?, b: Vector3?, t: number?) -> Vector3\|nil` | safe | Linear interpolation between two Vec3 points by t clamped to [0,1]; nil when either Vec3 is missing. |
| `ability_cast_start_time` | `HERO_LIB.ability_cast_start_time(ability: Ability\|integer) -> number` | safe | Server-time timestamp of the ability's current cast start, or 0 when the ability doesn't resolve. |
| `ability_index` | `HERO_LIB.ability_index(ability: Ability\|integer) -> integer` | safe | Ability index of the resolved ability, or 0 when it doesn't resolve. |
| `item_ready_by_slot` | `HERO_LIB.item_ready_by_slot(ability: Ability\|integer, countCastDelay: boolean?, acceptedOrders: table?) -> boolean,boolean` | safe | Readiness probe for an ability or slot; the second arg counts cast delay against readiness and the optional table lists accepted ECitadelAbilityOrders (names or ints). Returns ready, casting. |
| `ability_charge_cooldown` | `HERO_LIB.ability_charge_cooldown(ability: Ability) -> number` | safe | Scaled AbilityCooldownBetweenCharge (seconds between recovering charges), or 0 when the ability is invalid. |
| `ability_projectile_speed` | `HERO_LIB.ability_projectile_speed(ability: Ability) -> number` | safe | Resolved projectile speed in units/second, or 0 when the ability is invalid or has no projectile. |
| `can_cast_abilities_v2` | `HERO_LIB.can_cast_abilities_v2(pawn: PlayerPawn?) -> boolean` | safe | True when the pawn (local pawn by default) is free to initiate ability casts. |
| `QUICKCAST_MODE.DEFAULT` | `.QUICKCAST_MODE.DEFAULT: integer` | safe | Quickcast selector meaning 'use the ability's own default cast mode'. |
| `is_rift_buffed` | `HERO_LIB.is_rift_buffed(ent: Entity) -> boolean` | safe | True when the entity carries the CCitadel_Modifier_KothTrooperBuff rift buff. |
| `clear_aimbot_target` | `HERO_LIB.clear_aimbot_target() -> nil` | safe | Drops the owning script's manual PSilent target and clears the stored aimbot target. |
| `get_ground_jump_state` | `HERO_LIB.get_ground_jump_state() -> table\|nil` | safe | Table {grounded, ready, command, tick} from the latest jump prediction, or nil when prediction is stale or the call is off the game thread. |
| `mem_use` | `HERO_LIB.mem_use() -> integer` | safe | Current Lua heap usage in bytes (lua_gc GCCOUNT*1024 + GCCOUNTB). |
| `on_screen` | `HERO_LIB.on_screen(pos: Vector3) -> boolean` | safe | True when the world point projects onto the current viewport; false when pos isn't a vector. |
| `time_to_reach` | `HERO_LIB.time_to_reach(distance: number, speed: number) -> number` | safe | distance / speed, or 0 when speed is non-positive. |
| `INNATE.SLIDE` | `.INNATE.SLIDE: integer` | safe | Innate-action id for Slide. |
| `frame_time` | `HERO_LIB.frame_time() -> number` | safe | Seconds per server tick (tick interval). |
| `is_calico` | `HERO_LIB.is_calico() -> boolean` | safe | True when the local hero is Calico. |
| `is_mirage` | `HERO_LIB.is_mirage() -> boolean` | safe | True when the local hero is Mirage. |
| `is_yamato` | `HERO_LIB.is_yamato() -> boolean` | safe | True when the local hero is Yamato. |
| `max_mana` | `HERO_LIB.max_mana() -> number\|nil` | safe | Maximum value of the local pawn's ability-resource pool, or nil when it can't be read. |
| `get_modifier` | `HERO_LIB.get_modifier(pawn: PlayerPawn, name: string?) -> table\|nil` | safe | Snapshot table of the named modifier on the pawn (name, stack, buildup, duration, remaining, caster_index, ability_index, start_time, id, team, disabled, in_aura_range), or nil when it isn't present. |
| `modifier_stack_count` | `HERO_LIB.modifier_stack_count(pawn: PlayerPawn, name: string?) -> integer` | safe | Stack count of the named modifier on the pawn, or 0 when it isn't present. |
| `MOD_STATE.COMMAND_RESTRICTED` | `.MOD_STATE.COMMAND_RESTRICTED: integer` | safe | Live modifier-state bit for COMMAND_RESTRICTED. |
| `MOD_STATE.DISARMED` | `.MOD_STATE.DISARMED: integer` | safe | Live modifier-state bit for DISARMED. |
| `MOD_STATE.HEALTH_REGEN_DISABLED` | `.MOD_STATE.HEALTH_REGEN_DISABLED: integer` | safe | Live modifier-state bit for HEALTH_REGEN_DISABLED. |
| `MOD_STATE.IN_FRIENDLY_BASE` | `.MOD_STATE.IN_FRIENDLY_BASE: integer` | safe | Live modifier-state bit for IN_FRIENDLY_BASE. |
| `MOD_STATE.OBSCURED` | `.MOD_STATE.OBSCURED: integer` | safe | Live modifier-state bit for OBSCURED. |
| `MOD_STATE.SLOWED` | `.MOD_STATE.SLOWED: integer` | safe | Live modifier-state bit for SLOWED. |
| `MOD_STATE.TECH_UNTARGETABLE_BY_TEAMMATES` | `.MOD_STATE.TECH_UNTARGETABLE_BY_TEAMMATES: integer` | safe | Live modifier-state bit for TECH_UNTARGETABLE_BY_TEAMMATES. |
| `damage_movement_penalty_immune` | `HERO_LIB.damage_movement_penalty_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DAMAGE_MOVEMENT_PENALTY_IMMUNE modifier state. |
| `has_hollow_point` | `HERO_LIB.has_hollow_point(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HAS_HOLLOW_POINT_BULLETS modifier state. |
| `is_air_dashing` | `HERO_LIB.is_air_dashing(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the AIR_DASHING modifier state. |
| `is_command_restricted` | `HERO_LIB.is_command_restricted(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the COMMAND_RESTRICTED modifier state. |
| `is_disarmed` | `HERO_LIB.is_disarmed(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the DISARMED modifier state. |
| `is_hp_regen_disabled` | `HERO_LIB.is_hp_regen_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the HEALTH_REGEN_DISABLED modifier state. |
| `is_in_friendly_base` | `HERO_LIB.is_in_friendly_base(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the IN_FRIENDLY_BASE modifier state. |
| `is_mantle_disabled` | `HERO_LIB.is_mantle_disabled(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the MANTLE_DISABLED modifier state. |
| `is_out_of_game` | `HERO_LIB.is_out_of_game(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the OUT_OF_GAME modifier state. |
| `is_silenced_hidden` | `HERO_LIB.is_silenced_hidden(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SILENCED_HIDDEN modifier state. |
| `is_status_immune` | `HERO_LIB.is_status_immune(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the STATUS_IMMUNE modifier state. |
| `is_visible_to_enemy` | `HERO_LIB.is_visible_to_enemy(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the VISIBLE_TO_ENEMY modifier state. |
| `shooting_forced_on` | `HERO_LIB.shooting_forced_on(pawn: PlayerPawn) -> boolean` | safe | True when the pawn currently has the SHOOTING_FORCED_ON modifier state. |
| `TEAM.SPECTATOR` | `.TEAM.SPECTATOR: integer` | safe | Team id for the spectator team. |
| `hp_delta` | `HERO_LIB.hp_delta(pawn: PlayerPawn) -> integer` | safe | Missing health (max_health − health) of the pawn, or 0 when its facts can't be read. |
| `is_teammate_of` | `HERO_LIB.is_teammate_of(a: PlayerPawn, b: PlayerPawn) -> boolean` | safe | True when both pawns resolve and share a team. |
| `pawn_index` | `HERO_LIB.pawn_index(pawn: PlayerPawn?) -> integer` | safe | Entity index of the pawn (local pawn by default), or -1 when it can't be read. |
| `predict_position` | `HERO_LIB.predict_position(pawn: PlayerPawn, dt: number?) -> Vector3\|nil` | safe | Pawn origin advanced by dt seconds along its current velocity, or nil when the pawn's facts aren't available. |
| `allies` | `HERO_LIB.allies() -> table` | safe | Light-userdata list of player pawns the frame considers allied to the local pawn; empty when there's no local pawn. |
| `count_allies_in_radius` | `HERO_LIB.count_allies_in_radius(center: Vector3?, radius: number?) -> integer` | safe | Count of ally pawns within radius (default 1000 units) of center, defaulting to the local pawn's origin. |
| `nearest_ally` | `HERO_LIB.nearest_ally() -> PlayerPawn\|nil` | safe | Closest ally player pawn to the local pawn, or nil when none is tracked. |
| `angle_between_deg` | `HERO_LIB.angle_between_deg(a: Vector3, b: Vector3) -> number` | safe | Angle in degrees between two direction vectors, or 0 when either argument isn't a vector. |
| `distance` | `HERO_LIB.distance(a: PlayerPawn\|Vector3, b: PlayerPawn\|Vector3) -> number` | safe | 3D distance between two Vector3 points or two pawn origins; 0 when neither pairing resolves. |
| `normalize` | `HERO_LIB.normalize(v: Vector3) -> Vector3` | safe | Unit-length vector in v's direction, or the zero vector when its length is zero. |
| `pos_normalize` | `HERO_LIB.pos_normalize(v: Vector3) -> Vector3\|nil` | safe | Unit vector of v (zero vector when v's length is near zero), or nil when the argument isn't a vector. |

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
| `in_out_back` | `ANIM_LIB.in_out_back(t: number) -> number` | safe | Back-ease-in-out curve applied to progress `t`. |
| `smoothstep` | `ANIM_LIB.smoothstep(t: number) -> number` | safe | Hermite smoothstep (3t² − 2t³) applied to progress `t`. |
| `ease_in` | `ANIM_LIB.ease_in(t: number) -> number` | safe | Alias of `ANIM_LIB.in_cubic`. Cubic ease-in of `t`. |
| `in_out_expo` | `ANIM_LIB.in_out_expo(t: number) -> number` | safe | Exponential ease-in/out of `t`. |
| `value` | `ANIM_LIB.value(key: string, target: number, speed: number\|nil) -> number` | safe | Per-script keyed smoothing: initializes the state at `target` on first touch, then eases the stored value toward `target` by `clamp01(speed * dt)` (default speed 1); returns the new smoothed value. |
| `ease_in_out` | `ANIM_LIB.ease_in_out(t: number) -> number` | safe | Cubic ease-in-out curve applied to `t`. |
| `in_out_quint` | `ANIM_LIB.in_out_quint(t: number) -> number` | safe | Quintic ease-in-out curve applied to `t`. |
| `ease_out` | `ANIM_LIB.ease_out(t: number) -> number` | safe | Cubic ease-out curve (same as `out_cubic`). |
| `in_out_sine` | `ANIM_LIB.in_out_sine(t: number) -> number` | safe | Sine ease-in-out curve. |
| `in_quint` | `ANIM_LIB.in_quint(t: number) -> number` | safe | InQuint easing applied to t. |
| `in_sine` | `ANIM_LIB.in_sine(t: number) -> number` | safe | Returns easing::InSine(t). |
| `lerp` | `ANIM_LIB.lerp(a: number, b: number, t: number) -> number` | safe | Linearly interpolates from `a` to `b` by `t` (not clamped). |
| `lerp_angle` | `ANIM_LIB.lerp_angle(a: number, b: number, t: number) -> number` | safe | Linearly interpolates between the two angles in degrees, taking the shortest arc. |
| `out_back` | `ANIM_LIB.out_back(t: number) -> number` | safe | OutBack easing: overshoots past 1 before settling back. |
| `out_cubic` | `ANIM_LIB.out_cubic(t: number) -> number` | safe | Cubic ease-out of `t`. |
| `out_expo` | `ANIM_LIB.out_expo(t: number) -> number` | safe | Top-level easing: exponential ease-out curve (same function as `ANIM_LIB.easings.out_expo`). |
| `out_quint` | `ANIM_LIB.out_quint(t: number) -> number` | safe | Quintic ease-out. |
| `fade` | `ANIM_LIB.fade(key: string, target: number, speed: number?) -> number` | safe | Animation helper that eases a per-script named value toward `target` on each call and returns its current value. |
| `out_sine` | `ANIM_LIB.out_sine(t: number) -> number` | safe | Sine ease-out curve. |
| `in_back` | `ANIM_LIB.in_back(t: number) -> number` | safe | Evaluates the InBack easing on t (overshooting ease-in). |
| `reset` | `ANIM_LIB.reset(key: string)` | safe | Clears the animation state entry stored under the given (script-scoped) key. |
| `in_cubic` | `ANIM_LIB.in_cubic(t: number) -> number` | safe | Applies the InCubic easing curve to t and returns the result (`easing::InCubic(t)`). |
| `reset_all` | `ANIM_LIB.reset_all()` | safe | Clears every anim-lib stored value owned by the calling script's namespace (per-key smoothing state used by `value`, `fade`, `calculate_value`, etc.). |
| `in_expo` | `ANIM_LIB.in_expo(t: number) -> number` | safe | Exponential ease-in curve evaluated at t. |
| `smootherstep` | `ANIM_LIB.smootherstep(t: number) -> number` | safe | Smootherstep curve evaluated at t (6t^5 - 15t^4 + 10t^3). |

### Render

`table` · tier `safe` — 2D/3D drawing surface.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `DrawText` | `Render.DrawText(x: number, y: number, text: string, color: Color, fontHandle?: integer, align?: integer)` | safe | Optional Render.TEXT_ALIGN_* (default center). |
| `Text` | `Render.Text(font: integer, size: number, text: string, pos: Vec2, color: Color, align?: integer)` | safe | Font-first draw honoring the handle's family+weight at the per-call size; also accepts (x,y,text,color[,font,align]). Optional Render.TEXT_ALIGN_* (default center). |
| `DrawLine` | `Render.DrawLine(x1: number, y1: number, x2: number, y2: number, color: Color, thickness: number)` | safe | Draws a 2D line from (x1,y1) to (x2,y2) in the given color, with optional thickness (defaults to 1). |
| `Line` | `Render.Line(x1: number, y1: number, x2: number, y2: number, color: Color, thickness: number)` | safe | Also accepts (p1:Vec2, p2:Vec2, color[, thickness]). |
| `DrawBox` | `Render.DrawBox(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe | Draws an outlined 2D rectangle from (x1,y1) to (x2,y2) in the given color, with optional thickness (defaults to 1). |
| `Rect` | `Render.Rect(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe | Alias of DrawBox. |
| `DrawFilledBox` | `Render.DrawFilledBox(x1: number, y1: number, x2: number, y2: number, color: Color)` | safe | Draws a filled 2D rectangle from (x1,y1) to (x2,y2) in the given color. |
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
| `DrawCircle` | `Render.DrawCircle(x: number, y: number, radius: number, color: Color)` | safe | Draws an outlined 2D circle at (cx,cy) with the given radius and color, with optional thickness (defaults to 1). |
| `Circle` | `Render.Circle(x: number, y: number, radius: number, color: Color)` | safe | Also accepts (center:Vec2, radius, color). See Render.CircleArc for rings/arcs with thickness. |
| `DrawFilledCircle` | `Render.DrawFilledCircle(x: number, y: number, radius: number, color: Color)` | safe | Draws a filled 2D circle at (cx,cy) with the given radius and color. |
| `FilledCircle` | `Render.FilledCircle(x: number, y: number, radius: number, color: Color)` | safe | Alias of DrawFilledCircle. |
| `DrawCircle3D` | `Render.DrawCircle3D(center: Vector3, radius: number, color: Color)` | safe | Draws a world-space circle at the given center position with the specified radius and color, projected to screen. |
| `DrawLine3D` | `Render.DrawLine3D(start: Vector3, finish: Vector3, color: Color, thickness: number)` | safe | Draws a world-space line between two Vector3 endpoints in the given color, with optional thickness (defaults to 1). |
| `GetScreenSize` | `Render.GetScreenSize() -> table` | safe | Returns { width, height }. |
| `ScreenSize` | `Render.ScreenSize() -> table` | safe | Returns { width, height }. |
| `GetScreenCenter` | `Render.GetScreenCenter() -> table` | safe | Returns { x, y }. |
| `GetFPS` | `Render.GetFPS() -> number` | safe | Rendered frames per second: ImGui's average over the measured frame times, published once per frame. 0 before the first frame; reading it changes nothing. |
| `GetFrameTime` | `Render.GetFrameTime() -> number` | safe | Seconds per rendered frame, 1 / GetFPS (0 before the first frame). |
| `GetDeltaTime` | `Render.GetDeltaTime() -> number` | safe | The engine tick interval (about 1/64 s), not the frame time: use GetFrameTime for that. |
| `PresentCount` | `Render.PresentCount() -> integer` | safe | Frames the overlay has rendered since injection. |
| `TextCentered` | `Render.TextCentered(text: string, x: number, y: number, color: Color)` | safe | Draws text horizontally and vertically centred at (x,y) using the default font and the given color. |
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
| `ImageSize` | `ImageSize` | safe | Given an image handle, returns a table {x = width, y = height}; both are 0 if the handle is unknown. |
| `ImageCentered` | `ImageCentered` | safe | Draws a previously-loaded image centred on the given point, with optional size, tint color, four UVs, flags and corner rounding. |
| `FindOrCreateRT` | `Render.FindOrCreateRT(name: string, w: number, h: number) -> integer` | safe | Stable render-target handle per name. |
| `RenderToRT` | `Render.RenderToRT(rt: integer, fn: function)` | safe | Store a draw closure for the RT. |
| `DrawRT` | `Render.DrawRT(rt: integer, pos?: Vec2, size?: Vec2)` | safe | Re-invoke the RT's stored closure as fn(pos,size). |
| `PolygonFilled` | `PolygonFilled` | safe | Draws a filled convex polygon from a table of {x,y} points in the given color; a no-op if the active draw list is unavailable or the point count is below 3. |
| `Polyline` | `Polyline` | safe | Draws a polyline through a table of {x,y} points in the given color, with optional thickness (defaults to 1) and closed flag; a no-op if the active draw list is unavailable or the point count is below 2. |
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
| `PushTransform` | `Render.PushTransform(scale_x: number?, scale_y: number?, offset_x: number?, offset_y: number?) -> boolean` | safe | Reserved stub; the overlay has no transform stack, so this always returns false and does nothing. |
| `SetDefaultFont` | `Render.SetDefaultFont(handle: integer)` | safe | Chooses which registered font handle `Render.Text` falls back to when no explicit font is supplied. |
| `ShowHitboxesEnabled` | `Render.ShowHitboxesEnabled() -> boolean` | safe | Alias of `Render.ShowVisualsEnabled`. Returns true when the overlay visuals master switch is on. |
| `Bezier` | `Render.Bezier(x0: number, y0: number, x1: number, y1: number, x2: number, y2: number, x3: number, y3: number, color: Color, segments: integer?, thickness: number?)` | safe | Draws a cubic Bezier polyline from the four control points; `segments` is clamped to [2, 256] (default 20) and `thickness` defaults to 1. |
| `DrawFilledPolygon` | `Render.DrawFilledPolygon(verts: table, color: Color)` | safe | Draws a filled polygon from the vertex list in verts. |
| `DrawFilledRect` | `Render.DrawFilledRect(x1: number, y1: number, x2: number, y2: number, color: Color) -> nil` | safe | Alias of Render.DrawFilledBox: fills the axis-aligned rectangle in the given color. |
| `DrawFilledTriangle` | `Render.DrawFilledTriangle(ax: number, ay: number, bx: number, by: number, cx: number, cy: number, color: Color) -> nil` | safe | Queues a filled 2D triangle in `color`. |
| `DrawArrow3D` | `Render.DrawArrow3D(from: Vector3, to: Vector3, color: Color, thickness: number\|nil)` | safe | Draws a 3D arrow line from `from` to `to`; `thickness` defaults to 1. |
| `DrawImage` | `Render.DrawImage(handle: integer, x: number, y: number, w: number, h: number, tint: Color\|nil)` | safe | Draws the image identified by `handle` at `(x, y)` sized `(w, h)`; `tint` defaults to white. |
| `DrawPolygon` | `Render.DrawPolygon(verts: table, color: Color, thickness: number\|nil)` | safe | Draws a polygon outline through the vertex list `verts`; `thickness` defaults to 1. |
| `DrawBox3D` | `Render.DrawBox3D(mins: Vector3, maxs: Vector3, color: Color, thickness: number?)` | safe | Enqueues a 3D wireframe box between the two world-space corners (thickness defaults to 1). |
| `DrawImageRotated` | `Render.DrawImageRotated(handle: integer, x: number, y: number, w: number, h: number, rotation: number, tint: Color?)` | safe | Draws image `handle` at (x,y) with size (w,h), rotated by `rotation` radians; tint defaults to white. |
| `DrawRect` | `Render.DrawRect(x1: number, y1: number, x2: number, y2: number, color: Color, thickness: number?)` | safe | Alias of `Render.DrawBox`; draws an outlined screen-space rectangle between the two corners (thickness defaults to 1). |
| `DrawSphere3D` | `Render.DrawSphere3D(center: Vector3, radius: number, color: Color) -> nil` | safe | Submits a wire 3D sphere centered on `center` with the given radius and color through the world draw sink. |
| `FreeImage` | `Render.FreeImage(handle: integer) -> nil` | safe | Releases the Lua image slot (and its underlying D3D shader-resource view) for the given handle. |
| `DrawTextW` | `Render.DrawTextW(x: number, y: number, text: string, color: Color, font: integer?, align: integer?) -> nil` | safe | Alias of `Render.DrawText`. |
| `ScreenToWorld` | `Render.ScreenToWorld(sx: number, sy: number) -> Vector3` | safe | Unprojects a screen-space pixel coordinate back into a world-space direction/position (zero vector when projection is unavailable). |
| `GetImageSize` | `Render.GetImageSize(handle: integer) -> table` | safe | Returns a `{width, height}` table for the image handle; unknown handles yield zeros. |
| `DrawTriangle` | `Render.DrawTriangle(ax: number, ay: number, bx: number, by: number, cx: number, cy: number, color: Color, thickness: number?)` | safe | Queues a screen-space triangle outline through the three points; thickness defaults to 1. |
| `LoadImageFromURL` | `Render.LoadImageFromURL(url: string) -> integer` | safe | Stub that returns 0 for any URL (URL image loading is not implemented). |
| `FrostedFill` | `Render.FrostedFill(p1: any, p2: any, strength: number\|nil, alpha: number\|nil, rounding: number\|nil)` | safe | Draws a frosted/blurred fill in the rectangle from `p1` to `p2`; `strength`, `alpha`, and `rounding` default to 1, 1, and 0. |
| `IsPointInBox` | `Render.IsPointInBox(px: number, py: number, x1: number, y1: number, x2: number, y2: number) -> boolean` | safe | True when point (px, py) lies inside the axis-aligned rectangle from (x1, y1) to (x2, y2). |
| `Path` | `Render.Path(verts: table, color: Color, thickness: number?) -> nil` | safe | Alias of `Render.DrawPolygon`; strokes an open polyline through the given vertices. |
| `LoadImageFromFile` | `Render.LoadImageFromFile(path: string) -> integer` | safe | Alias of `Render.LoadImage`; loads/caches an image (SVG routed via vsvg) and returns a Lua image handle, 0 on failure. |
| `PopClipRect` | `Render.PopClipRect()` | safe | Pops the clip rect pushed by a prior Render.PushClipRect. |
| `LoadFontFromFile` | `Render.LoadFontFromFile(path: string, size?: integer, weight?: integer) -> integer` | safe | Alias of `Render.LoadFontFile`; registers a font loaded from path (parsed family, bold-default weight) and returns a font handle, 0 on failure. |
| `PopTransform` | `Render.PopTransform() -> boolean` | safe | No-op stub (the transform stack is not exposed); always returns false. |
| `MeasureText` | `Render.MeasureText(text: string, fontHandle: integer\|nil, size: number\|nil) -> table` | safe | Returns a table with numeric `width` and `height` fields giving the rendered size of `text` at the given font handle (its stored size is used if `size` is omitted) or at the fallback script-font size. |
| `PushClipRect` | `Render.PushClipRect(x1: number, y1: number, x2: number, y2: number, intersect: boolean\|nil)` | safe | Pushes a clip rect onto the ImGui draw list; `intersect` defaults to true (intersect with any current clip). |
| `RegisterFontFamily` | `Render.RegisterFontFamily(family: string, path: string\|nil, weight: integer\|nil, size: number\|nil) -> integer` | safe | Registers a font family (optionally from a file path) and returns a handle for the given weight/size; defaults are regular weight and 12 px. |

### Menu

`table` · tier `safe` — Menu tree entry points (Create/Find/Tab) + style/state.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Create` | `Menu.Create(a: string, b?: string, c?: string, d?: string, e?: string) -> MenuNode` | safe | Build/find a menu path; a hero script's path is auto-re-rooted under Heroes/Hero List/<hero>. |
| `Find` | `Menu.Find(a: string, b?: string, c?: string, d?: string, e?: string, f?: string) -> MenuNode\|nil` | safe | Walks the given path segments through the menu tree and returns the matching MenuNode, or an empty MenuNode if any segment is missing. |
| `Tab` | `Menu.Tab(name: string) -> MenuNode` | safe | Returns the root tab MenuNode with the given name, creating it if it does not already exist. |
| `Style` | `Menu.Style(name?: string) -> Color\|table` | safe | Themed color for a palette name (primary/text/background/shadow + aliases); no arg returns the full theme table. |
| `Opened` | `Menu.Opened() -> boolean` | safe | Returns true while the Avalanche overlay menu is currently visible. |
| `Panel` | `Menu.Panel(row: MenuNode, opts: table) -> MenuPanel\|nil` | safe | A HUD panel placement owned by one of the script's Switch or Combo rows, kept like the native overlays' (a screen cell + offset, or a dragged position; own or HUD scale and opacity) and edited from the row's "...". opts = { id (1-31 of a-z 0-9 _), cell (0..8, top-left to bottom-right row by row; default 4) }. nil after a console error. |

### Preview

`table` · tier `safe` — ESP preview plate integration: scripts draw their own elements on the in-menu preview plate and register toggles in its element checklist. Register with Preview.register_element(key, label, default_on); the returned token drives Preview.is_element_enabled. Preview.on_draw(fn) fires every frame the plate is visible with a plate table { x, y, w, h } in screen pixels; use the regular draw.* primitives inside — they are retargeted to the plate's own drawlist and clipped to the stage. Elements are bound to the script that registered them and cleared on unload.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `register_element` | `Preview.register_element(key: string, label: string, default_on: boolean?) -> integer` | safe | Register a new entry in the preview plate's element checklist (next to Name, Health Bar, etc). key is a stable per-script id. label is the text shown in the chip. default_on seeds the initial state (default false). Returns a token to pass to Preview.is_element_enabled / Preview.set_element_enabled / Preview.unregister_element. Re-registering the same (script, key) updates the label and returns the existing token. Elements are cleared on script unload. Returns 0 on bad arguments. |
| `is_element_enabled` | `Preview.is_element_enabled(token: integer) -> boolean` | safe | Current enabled state of a registered element. Scripts should guard their Preview.on_draw painting with this so the user's toggle in the plate chip-row actually takes effect. |
| `set_element_enabled` | `Preview.set_element_enabled(token: integer, on: boolean)` | safe | Script-side override of a registered element's enabled state. The user's click on the chip remains authoritative; this is for seeding presets or exposing Preview toggles through the hero config. |
| `unregister_element` | `Preview.unregister_element(token: integer)` | safe | Remove an element from the plate's checklist. Normally unnecessary: elements are cleared automatically on script unload. |
| `on_draw` | `Preview.on_draw(fn: function) -> integer` | safe | Install a callback that fires every frame the ESP preview plate is visible. The plate table carries the stage rect in screen pixels. draw.* calls inside the callback paint onto the plate's own drawlist (clipped to the stage), so they land above the hero model and below the plate's chrome/element overlays. Returns a handler id. |

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
| `ClearManualTarget` | `Aim.ClearManualTarget()` | safe | Clears any manual PSilent target set via Aim.SetManualTarget. |
| `LastCommitTick` | `Aim.LastCommitTick() -> integer` | safe | Returns the server tick at which PSilent last committed its fake viewangles. |
| `LastFake` | `Aim.LastFake() -> Vector3` | safe | Last fake-angle view direction committed by the pSilent system. |
| `LocalHeroId` | `Aim.LocalHeroId() -> integer` | safe | Returns the local player's hero id, or -1 when no local entity is tracked. |
| `NormalEnabled` | `Aim.NormalEnabled() -> boolean` | safe | True while the Normal aim activation flag is set in the current aim-mode mask. |
| `PSilentEnabled` | `Aim.PSilentEnabled() -> boolean` | safe | True when the current aim mode has the P-Silent activation bit set. |
| `PSilentReach` | `Aim.PSilentReach() -> number` | safe | Returns the currently-active psilent reach distance. |
| `PSilentSucceeded` | `Aim.PSilentSucceeded() -> boolean` | safe | Returns true when the last PSilent commit succeeded this tick. |
| `SetManualTarget` | `Aim.SetManualTarget(pos: Vector3) -> boolean` | safe | Installs a manual psilent aim target at pos, attributed to the calling script; always returns true. |
| `WorldRadiusToPixel` | `Aim.WorldRadiusToPixel(worldRadius: number, distance: number) -> number` | safe | Projects a world-space radius onto the screen at the given view distance; returns `worldRadius` unchanged when distance <= 1, else `(worldRadius / distance) * ScreenUtils::PixelsPerTan()`. |

### callback

`table` · tier `safe` — Event channels. callback.on_<name> is a channel handle (:set / :add, see CallbackHandle); callback.add / once / throttled take the channel name. Every fire of a channel, whether from the game, a bridge event or callback.fire, runs its handlers in registration order and honours pause_script, set_channel_throttle, disable, once, throttled and the `when` gate. The menu, cursor and typing edges are recorded where they happen and delivered on the game thread at the next frame stage (in menus too, not during a map change); a state that flips back before then fires nothing.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_pre_createmove` | `on_pre_createmove` | safe | Channel handle for the pre_createmove channel; handlers receive the UserCmd just before any feature writes it (fired from InvokePreCreateMoveCallbacks on the game thread). |
| `on_createmove` | `on_createmove` | safe | Channel handle for the createmove channel; handlers receive this tick's UserCmd on the game thread after native features have written it. |
| `on_frame` | `on_frame` | safe | Channel handle for the frame channel; handlers run per rendered frame via Vm::DispatchFrame with no arguments. |
| `on_draw` | `on_draw` | safe | Channel handle for the draw channel; handlers run inside the overlay draw pass with no arguments and should issue only Render/ImGui calls. |
| `on_preview_draw` | `on_preview_draw` | safe | Channel handle for the ESP preview plate's own draw pass; handlers get (plate) where plate.x/y/w/h is the stage rect in screen pixels. draw.* primitives inside are retargeted to the plate's drawlist and clipped to the stage. Same channel Preview.on_draw installs onto. |
| `on_add_modifier` | `on_add_modifier` | safe | Channel handle; handlers get (mod, holder_handle, modifier, target, caster) (see the on_add_modifier event). NEW: an optional filter, :set(fn, { modifiers = { name, ... } }) (also :add and callback.add): the handler fires only for those modifier names (case-insensitive), checked natively before Lua runs; without it the handler gets every event. |
| `on_remove_modifier` | `on_remove_modifier` | safe | Channel handle; handlers get (mod, holder_handle, modifier_name, target, caster) (see the on_remove_modifier event). NEW: an optional filter, :set(fn, { modifiers = { name, ... } }) (also :add and callback.add): the handler fires only for those modifier names (case-insensitive), checked natively before Lua runs; without it the handler gets every event. |
| `on_bullet_create` | `on_bullet_create` | safe | Channel handle for the bullet_create channel; handlers receive a table (origin/start_pos, direction, angles, max_range, bullet_speed_override, weapon_subclass_id, ability_as_bullet, fired_from_gun, and when resolvable shooter/entity and weapon_name). |
| `on_particle_create` | `on_particle_create` | safe | Channel handle for the particle_create channel; handlers receive a table with particle_index, name/path/particle_path, index/handle/entity_index, is_local and a zero position (keyed by particle name hash). |
| `on_particle_update` | `on_particle_update` | safe | Channel handle for the particle_update channel; handlers receive a table with path/name/particle_path, index/handle/entity_index and position (keyed by particle name hash). |
| `on_particle_destroy` | `on_particle_destroy` | safe | Channel handle for the particle_destroy channel; handlers receive a table with path/name/particle_path and index/entity_index, plus released/immediate flags from the destroy event (keyed by particle name hash). |
| `on_take_damage` | `on_take_damage` | safe | Channel handle for the take_damage channel; handlers receive a table with attacker, victim, hitgroup, damage and ability_id. |
| `on_game_event` | `on_game_event` | safe | Channel handle for the game_event channel; handlers receive the event name and a payload table synthesised from the game-event fields. |
| `on_key` | `callback.on_key(code: integer, isDown: boolean) -> boolean\|nil` | safe | Fires for keyboard AND mouse buttons: mouse buttons report via the standard VK_* code (Keys.MOUSE1..MOUSE5 = VK_LBUTTON/VK_RBUTTON/VK_MBUTTON/VK_XBUTTON1/VK_XBUTTON2) with isDown=true/false on the button down/up transition. Return a truthy value to CLAIM the key/button (blocks it from the game and the menu/panic handlers). |
| `on_scroll` | `callback.on_scroll(delta: integer, horizontal: boolean) -> boolean\|nil` | safe | Mouse-wheel notch (WM_MOUSEWHEEL/WM_MOUSEHWHEEL). delta is signed WHEEL_DELTA(120) units; horizontal is true for the tilt-wheel/shift-scroll axis. Return a truthy value to CLAIM the wheel tick (mirrors on_key's block semantics) — e.g. a script's scroll region owning the notch instead of the underlying UI. |
| `on_entity_create` | `callback.on_entity_create(entity: Entity, idx: integer)` | safe | Global shorthand that installs the passed function as a handler on the entity_created channel; handlers run on the game thread with (entity, idx), the Entity object polymorphic over the real class (use :as_pawn()). |
| `on_entity_destroy` | `callback.on_entity_destroy(entity: Entity\|nil, idx: integer)` | safe | Global shorthand that installs the passed function as a handler on the entity_deleted channel; handlers run on the game thread with (entity\|nil, idx). |
| `on_sound` | `on_sound` | safe | Channel handle for the legacy sound channel; handlers receive (name, pos_x, pos_y, pos_z) each time a sound starts. |
| `on_scripts_loaded` | `on_scripts_loaded` | safe | Channel handle for the scripts_loaded channel; handlers fire once per script after every script's own on_scripts_loaded has run, and once more per script that loads later. |
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
| `context` | `callback.context() -> table` | safe | The dispatch running on this thread: { script, channel, depth, seq, global_seq }. script and channel name the handler being called ("(none)" outside a dispatch); depth counts the dispatches nested on this thread (0 outside one); seq counts the dispatch contexts entered and global_seq the channel fires, both since boot and on every thread. A menu change callback runs under its registering script's context, so script names that script rather than "(none)". |
| `pause_script` | `callback.pause_script(script: string) -> boolean` | safe | Stop calling the named script's handlers on every channel, game and bridge events included, until resume_script. Returns true. |
| `resume_script` | `callback.resume_script(script: string) -> boolean` | safe | Undo pause_script. Returns true. |
| `is_script_paused` | `callback.is_script_paused(script: string) -> boolean` | safe | Returns true when the named script is currently in the paused set (its handlers are skipped by MarkPausedRows); pass the script's registered name. |
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
| `cancel` | `callback.cancel(id: integer) -> boolean` | safe | Removes the deferred/periodic timer with the given id (as returned by `defer`/`every`). Returns true when the row was owned by the caller and erased, false otherwise. |
| `on_input` | `.on_input: CallbackHandle` | safe | Channel handle bound to the `input` channel; use `:add(fn)` / `:set(fn)` to subscribe, or call it as `callback.on_input(fn)` via the global shim. |
| `unset` | `callback.unset(channel: string)` | safe | Removes every handler owned by the calling script from the given channel and recomputes the dispatch mask. |
| `on_net_message` | `.on_net_message: CallbackHandle` | safe | Channel handle bound to the `net_message` channel for intercepting incoming game net messages. |
| `channel_owners` | `callback.channel_owners(channel: string\|nil) -> table` | safe | Returns an array of unique script owner names that currently have handlers registered on the given channel; empty table if none. |
| `on_input_key_down` | `.on_input_key_down: CallbackHandle` | safe | Channel handle for the `input_key_down` channel; fires on every key-down edge and passes the virtual-key code and `true` to handlers. |
| `on_post_createmove` | `.on_post_createmove: CallbackHandle` | safe | Channel handle for the `post_createmove` channel; fires after each CreateMove tick on the client. |
| `channel_stats` | `callback.channel_stats(channel: string) -> table` | safe | Returns per-channel dispatch stats for `channel` with fields `has_stats`, `fire_count`, `error_count`, `avg_us`, `max_us`, and `last_fire_ms_ago` (0 if never fired). |
| `on_input_key_up` | `.on_input_key_up: CallbackHandle` | safe | CallbackHandle bound to the `input_key_up` channel; use `:add(fn)` or `:set(fn)` to register a handler that fires when a key is released. |
| `on_round_end` | `.on_round_end: CallbackHandle` | safe | CallbackHandle bound to the `round_end` channel; use `:add(fn)` or `:set(fn)` to register a handler fired at round end. |
| `clear_errors` | `callback.clear_errors() -> boolean` | safe | Empties the recorded callback-error ring; always returns true. |
| `on_render` | `.on_render: CallbackHandle` | safe | CallbackHandle bound to the `render` channel; attach frame-render handlers with :add(fn) or :set(fn). |
| `on_round_start` | `.on_round_start: CallbackHandle` | safe | CallbackHandle bound to the `round_start` channel; fires at the start of each round. |
| `count` | `callback.count(channel: string) -> integer` | safe | Returns the number of handlers currently registered on the given channel, or 0 if the channel is unknown. |
| `recent_errors` | `callback.recent_errors(limit: integer?) -> table` | safe | Returns an array of up to limit (default 16, capped at 64) recent recorded script errors; each row has script, channel, message, when_ms. |
| `on_start_sound` | `.on_start_sound: CallbackHandle` | safe | Channel handle for the start_sound event; handlers receive a table with soundevent_hash, soundevent_guid, seed, networked, and (when available) position, name, and source entity. |
| `defer` | `callback.defer(delay_ms: integer, fn: function) -> integer` | safe | Schedules a one-shot timer that fires fn after delay_ms milliseconds and returns its id (0 if the second arg is not a function); cancel via callback.cancel(id). |
| `record_error` | `callback.record_error(script: string, channel: string, message: string) -> boolean` | safe | Appends an error row (script, channel, message, timestamp) to the bounded script-error ring (oldest entry evicted when the cap is reached) and returns true; all three args default to empty strings. |
| `on_user_message` | `callback.on_user_message(msg_id: integer)` | safe | Fires on the user_message channel after each incoming user message that no script tap swallowed, passing the engine message id. |
| `disable` | `callback.disable(channel: string, id: integer) -> boolean` | safe | Marks the handler row with the given id on `channel` disabled; returns true when a row was flipped. |
| `remove` | `callback.remove(channel: string, id: integer) -> boolean` | safe | Unregisters the handler row with the given id on `channel`, but only if the caller script owns it; returns true on success. |
| `drain_deferred` | `callback.drain_deferred() -> integer` | safe | Runs every deferred/every/throttled callback whose scheduled time has elapsed, then returns how many fired. |
| `remove_all` | `callback.remove_all(channel: string\|nil) -> integer` | safe | Removes all handlers the caller script owns on `channel` (empty string = the default channel), recomputes the channel mask, and returns the count cleared. |
| `drain_notifications` | `callback.drain_notifications() -> table` | safe | Atomically moves the pending-notification queue (populated by callback.notification) into a Lua table and returns it; each entry is {text=string, severity=integer}. |
| `reset_stats` | `callback.reset_stats() -> boolean` | safe | Clears per-channel fire/error/timing stats and zeroes every registered handler's fire/error counts; always returns true. |
| `on_connect` | `.on_connect: CallbackHandle` | safe | Channel handle for "connect": fires when the client finishes connecting to a server. |
| `enable` | `callback.enable(channel: string, id: integer) -> boolean` | safe | Re-enables a previously disabled handler row for `channel`/`id`; returns true if the row was found and cleared. |
| `script_channels` | `callback.script_channels(script: string) -> table` | safe | Returns an array of channel names on which the named script currently has at least one handler registered. |
| `on_disconnect` | `.on_disconnect: CallbackHandle` | safe | Channel handle for the client-disconnect event (channel `disconnect`); registered handlers fire once the client leaves the server. |
| `enumerate` | `callback.enumerate(channel: string) -> table` | safe | Returns an array of handler rows for the channel, each a table with id, script, fires, errors, throttle_ms, and disabled. Unknown channel yields an empty array. |
| `script_owns` | `callback.script_owns(channel: string, id: integer) -> boolean` | safe | Reports whether the handler id on the channel was registered by the calling script. |
| `on_entity_created` | `.on_entity_created: CallbackHandle` | safe | Callback handle for the `entity_created` channel, fired for each newly tracked entity. |
| `every` | `callback.every(periodMs: integer) -> integer` | safe | Registers a repeating script timer that fires every `periodMs` milliseconds (a zero period is clamped to 1); returns the timer id. |
| `set` | `callback.set(channel: string, fn: any) -> integer` | safe | Removes any handlers the calling script owns on `channel`, then installs `fn` as the replacement and returns the new row id; passing a non-function just performs the removal and returns 0. |
| `on_entity_deleted` | `.on_entity_deleted: CallbackHandle` | safe | Channel handle for `entity_deleted`; fires when an entity is removed. |
| `list_channels` | `callback.list_channels() -> table` | safe | Returns an array of names of channels that currently have at least one handler. |
| `snapshot` | `callback.snapshot() -> table` | safe | Returns a counts table: channel_count, entry_count, deferred_count, paused_count, error_count, dispatch_seq, notif_queue_size. |
| `on_game_end` | `callback.on_game_end(fn: function, opts: table?) -> integer` | safe | Attaches a handler on the `game_end` channel, fired when a match ends. |
| `list_deferred` | `callback.list_deferred() -> table` | safe | Returns an array of pending deferred/periodic entries, each row {id, script, when_ms (ms from now until fire, may be negative), period_ms (0 for one-shot)}. |
| `stats` | `callback.stats(channel: string) -> table` | safe | Returns {count, fire_count, error_count} totalled across every handler currently subscribed to the given channel. |
| `on_game_start` | `.on_game_start: CallbackHandle` | safe | Callback handle on the "game_start" channel; fires when a game begins. Use callback.on_game_start:add(fn) to subscribe. |
| `notification` | `callback.notification(msg: string, severity: integer\|nil)` | safe | Logs msg to the Lua console at the given severity (0 debug, 1 info, 2 warn, 3 error; clamped into that range, default 1) under the caller's identity and, unless notifications are internally suppressed, queues it onto the pending-notification queue (capped at 128 entries). |
| `total_channels` | `callback.total_channels() -> integer` | safe | Returns the number of distinct callback channels that currently have at least one registered handler. |
| `on_late_add_entity` | `callback.on_late_add_entity(entity: Entity)` | safe | Fires once per entity that was observed to appear outside the normal game-thread add path, drained on the game thread; the handler receives the resolved entity object. |
| `on_console_output` | `callback.on_console_output(fn: function) -> CallbackHandle` | safe | Channel that fires when console output is emitted; the handle registers a listener on the `console_output` channel. |
| `total_count` | `callback.total_count() -> integer` | safe | Sum of listener counts across every callback channel. |
| `on_map_change` | `callback.on_map_change(fn: function) -> CallbackHandle` | safe | Channel that fires on map change; the handle registers a listener on the `map_change` channel. |

### ImGui

`table` · tier `safe` — Immediate-mode GUI primitives.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Begin` | `Begin` | safe | Opens a window scope. A 65th nested Begin is refused (returns false) instead of overflowing the scope stack. |
| `End` | `End` | safe | Mirrors Dear ImGui `ImGui::End()` — closes the current window scope opened by Begin; a no-op when no window is open or when called off the frame thread. |
| `Window` | `Window` | safe | Scoped convenience wrapper around `ImGui::Begin`/`ImGui::End(name)` — calls the supplied body function inside the window and ends it automatically; no-op off the frame thread. |
| `CaptureInput` | `ImGui.CaptureInput()` | safe | Gives your windows the mouse and keyboard for this frame, the way the open menu has them: the cursor shows, mouse look pauses and the game stops receiving input. Call it from on_draw on every frame your interactive window is open (e.g. while your own toggle key has it shown); stop calling it and the game gets its input back on the next frame, so closing the window, unloading the script or a script error all release it. Never call it for a HUD or overlay window. Takes effect only while the game window has focus. |
| `SetNextWindowSize` | `SetNextWindowSize` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowSize(size, cond)` — sets the size of the next window (cond defaults to `ImGuiCond_Always`). |
| `SetNextWindowPos` | `SetNextWindowPos` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowPos(pos, cond)` — sets the position of the next window (cond defaults to `ImGuiCond_Always`). |
| `SetNextItemWidth` | `SetNextItemWidth` | safe | Mirrors Dear ImGui `ImGui::SetNextItemWidth(width)` — sets the width of the next common widget. |
| `Text` | `Text` | safe | Mirrors Dear ImGui `ImGui::TextUnformatted(text)` — displays the given string without printf-style formatting. |
| `TextWrapped` | `TextWrapped` | safe | Mirrors Dear ImGui `ImGui::TextWrapped(fmt, ...)` — text that wraps to the available content width. |
| `TextDisabled` | `TextDisabled` | safe | Mirrors Dear ImGui `ImGui::TextDisabled(fmt, ...)` — text rendered in the disabled style color. |
| `TextColored` | `TextColored` | safe | Mirrors Dear ImGui `ImGui::TextColored(col, text)` — colored text; accepts (r,g,b,text) or (r,g,b,a,text), alpha defaulting to 1. |
| `BulletText` | `BulletText` | safe | Mirrors Dear ImGui `ImGui::BulletText(fmt, ...)` — bullet marker followed by text on the same line. |
| `LabelText` | `LabelText` | safe | Mirrors Dear ImGui `ImGui::LabelText(label, text)` — displays text with a label on its right side. |
| `Separator` | `Separator` | safe | Mirrors Dear ImGui `ImGui::Separator()` — draws a horizontal line across the current content region. |
| `SeparatorText` | `SeparatorText` | safe | Mirrors Dear ImGui `ImGui::SeparatorText(label)` — a horizontal separator with a text label. |
| `Spacing` | `Spacing` | safe | Mirrors Dear ImGui `ImGui::Spacing()` — adds vertical spacing of one item height. |
| `NewLine` | `NewLine` | safe | Mirrors Dear ImGui `ImGui::NewLine()` — moves the layout cursor to the next line, undoing a prior SameLine. |
| `Bullet` | `Bullet` | safe | Mirrors Dear ImGui `ImGui::Bullet()` — draws a bullet marker and advances the cursor on the same line. |
| `Indent` | `Indent` | safe | Mirrors Dear ImGui `ImGui::Indent(width)` — pushes the layout cursor right by the given width (or the default when 0). |
| `Unindent` | `Unindent` | safe | Mirrors Dear ImGui `ImGui::Unindent(width)` — pops the layout cursor left by the given width (or the default when 0). |
| `SameLine` | `SameLine` | safe | Mirrors Dear ImGui `ImGui::SameLine(offset_from_start_x, spacing_w)` — keeps the next widget on the same line (spacing defaults to -1 for ImGui's default). |
| `Dummy` | `Dummy` | safe | Mirrors Dear ImGui `ImGui::Dummy(size)` — advances the layout cursor by an invisible item of the given size. |
| `Button` | `Button` | safe | Mirrors Dear ImGui `ImGui::Button(label, size)` — returns true the frame the button is clicked; optional size defaults to 0,0 (auto). |
| `SmallButton` | `SmallButton` | safe | Mirrors Dear ImGui `ImGui::SmallButton(label)` — compact button with no frame padding; returns true the frame it is clicked. |
| `Checkbox` | `Checkbox` | safe | Mirrors Dear ImGui `ImGui::Checkbox(label, value)` — returns the current value and a changed flag (value, changed). |
| `RadioButton` | `RadioButton` | safe | Mirrors Dear ImGui `ImGui::RadioButton(label, active)` — returns true the frame it is clicked. |
| `SliderFloat` | `SliderFloat` | safe | Mirrors Dear ImGui `ImGui::SliderFloat(label, value, min, max, format, flags)` — min/max are clamped to a valid range; returns (value, changed). |
| `SliderInt` | `SliderInt` | safe | Mirrors Dear ImGui `ImGui::SliderInt(label, value, min, max, format, flags)` — min/max are clamped to a valid range; returns (value, changed). |
| `DragFloat` | `DragFloat` | safe | Mirrors Dear ImGui `ImGui::DragFloat(label, value, speed, min, max, format, flags)` — speed defaults to 1; returns (value, changed). |
| `DragInt` | `DragInt` | safe | Mirrors Dear ImGui `ImGui::DragInt(label, value, speed, min, max, format, flags)` — speed defaults to 1; returns (value, changed). |
| `InputInt` | `InputInt` | safe | Mirrors Dear ImGui `ImGui::InputInt(label, value, step, step_fast, flags)` — returns (value, changed); user text callbacks are disabled for safety. |
| `InputFloat` | `InputFloat` | safe | Mirrors Dear ImGui `ImGui::InputFloat(label, value, step, step_fast, format, flags)` — returns (value, changed); user text callbacks are disabled for safety. |
| `InputText` | `InputText` | safe | Mirrors Dear ImGui `ImGui::InputText(label, text, max_len, flags)` — writes into a frame-scratch buffer; max_len defaults to 256 and is capped at the internal input-text byte limit; returns (text, changed), with callbacks disabled. |
| `Combo` | `Combo` | safe | Mirrors Dear ImGui `ImGui::Combo(label, current, items, popup_max_height)` — items is a Lua array; `current` is 1-based and clamped to the item range; returns (new_index, changed). |
| `ColorEdit` | `ColorEdit` | safe | Mirrors Dear ImGui `ImGui::ColorEdit3/4(label, col, flags)` — accepts an RGB/RGBA table (edited in place) or separate r,g,b[,a] numbers; returns the edited color plus changed. |
| `CollapsingHeader` | `CollapsingHeader` | safe | Mirrors Dear ImGui `ImGui::CollapsingHeader(label, flags)` — returns true when the section is open. |
| `ProgressBar` | `ProgressBar` | safe | Mirrors Dear ImGui `ImGui::ProgressBar(fraction, size, overlay)` — fraction in [0,1]; size defaults to (-FLT_MIN, 0) (fill width, auto height). |
| `IsItemHovered` | `IsItemHovered` | safe | Mirrors Dear ImGui `ImGui::IsItemHovered()` — true if the previously submitted item is being hovered this frame. |
| `IsItemClicked` | `IsItemClicked` | safe | Mirrors Dear ImGui `ImGui::IsItemClicked()` — true the frame the previously submitted item is clicked with the left mouse button. |
| `SetTooltip` | `SetTooltip` | safe | Mirrors Dear ImGui `ImGui::SetTooltip(fmt, ...)` — sets a tooltip popup for the current hovered item. |
| `GetContentRegionAvail` | `GetContentRegionAvail` | safe | Mirrors Dear ImGui `ImGui::GetContentRegionAvail()` — returns the available content region size as (x, y). |
| `AlignTextToFramePadding` | `ImGui.AlignTextToFramePadding()` | safe | Mirrors Dear ImGui `ImGui::AlignTextToFramePadding`. See the Dear ImGui documentation for parameters and behaviour. |
| `ArrowButton` | `ImGui.ArrowButton()` | safe | Mirrors Dear ImGui `ImGui::ArrowButton`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginChild` | `ImGui.BeginChild()` | safe | Mirrors Dear ImGui `ImGui::BeginChild`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginCombo` | `ImGui.BeginCombo()` | safe | Mirrors Dear ImGui `ImGui::BeginCombo`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginGroup` | `ImGui.BeginGroup()` | safe | Mirrors Dear ImGui `ImGui::BeginGroup`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginListBox` | `ImGui.BeginListBox()` | safe | Mirrors Dear ImGui `ImGui::BeginListBox`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginMainMenuBar` | `ImGui.BeginMainMenuBar()` | safe | Mirrors Dear ImGui `ImGui::BeginMainMenuBar`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginMenu` | `ImGui.BeginMenu()` | safe | Mirrors Dear ImGui `ImGui::BeginMenu`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginMenuBar` | `ImGui.BeginMenuBar()` | safe | Mirrors Dear ImGui `ImGui::BeginMenuBar`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginPopup` | `ImGui.BeginPopup()` | safe | Mirrors Dear ImGui `ImGui::BeginPopup`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginPopupContextItem` | `ImGui.BeginPopupContextItem()` | safe | Mirrors Dear ImGui `ImGui::BeginPopupContextItem`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginPopupContextWindow` | `ImGui.BeginPopupContextWindow()` | safe | Mirrors Dear ImGui `ImGui::BeginPopupContextWindow`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginPopupModal` | `ImGui.BeginPopupModal()` | safe | Mirrors Dear ImGui `ImGui::BeginPopupModal`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginTabBar` | `ImGui.BeginTabBar()` | safe | Mirrors Dear ImGui `ImGui::BeginTabBar`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginTabItem` | `ImGui.BeginTabItem()` | safe | Mirrors Dear ImGui `ImGui::BeginTabItem`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginTable` | `ImGui.BeginTable()` | safe | Mirrors Dear ImGui `ImGui::BeginTable`. See the Dear ImGui documentation for parameters and behaviour. |
| `BeginTooltip` | `ImGui.BeginTooltip()` | safe | Mirrors Dear ImGui `ImGui::BeginTooltip`. See the Dear ImGui documentation for parameters and behaviour. |
| `CalcItemWidth` | `ImGui.CalcItemWidth()` | safe | Mirrors Dear ImGui `ImGui::CalcItemWidth`. See the Dear ImGui documentation for parameters and behaviour. |
| `CalcTextSize` | `ImGui.CalcTextSize()` | safe | Mirrors Dear ImGui `ImGui::CalcTextSize`. See the Dear ImGui documentation for parameters and behaviour. |
| `CheckboxFlags` | `ImGui.CheckboxFlags()` | safe | Mirrors Dear ImGui `ImGui::CheckboxFlags`. See the Dear ImGui documentation for parameters and behaviour. |
| `CloseCurrentPopup` | `ImGui.CloseCurrentPopup()` | safe | Mirrors Dear ImGui `ImGui::CloseCurrentPopup`. See the Dear ImGui documentation for parameters and behaviour. |
| `ColorButton` | `ImGui.ColorButton()` | safe | Mirrors Dear ImGui `ImGui::ColorButton`. See the Dear ImGui documentation for parameters and behaviour. |
| `ColorEdit3` | `ImGui.ColorEdit3()` | safe | Mirrors Dear ImGui `ImGui::ColorEdit3`. See the Dear ImGui documentation for parameters and behaviour. |
| `ColorEdit4` | `ImGui.ColorEdit4()` | safe | Mirrors Dear ImGui `ImGui::ColorEdit4`. See the Dear ImGui documentation for parameters and behaviour. |
| `ColorPicker3` | `ImGui.ColorPicker3()` | safe | Mirrors Dear ImGui `ImGui::ColorPicker3`. See the Dear ImGui documentation for parameters and behaviour. |
| `ColorPicker4` | `ImGui.ColorPicker4()` | safe | Mirrors Dear ImGui `ImGui::ColorPicker4`. See the Dear ImGui documentation for parameters and behaviour. |
| `DockSpace` | `ImGui.DockSpace()` | safe | Mirrors Dear ImGui `ImGui::DockSpace`. See the Dear ImGui documentation for parameters and behaviour. |
| `DockSpaceOverViewport` | `ImGui.DockSpaceOverViewport()` | safe | Mirrors Dear ImGui `ImGui::DockSpaceOverViewport`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragFloat2` | `ImGui.DragFloat2()` | safe | Mirrors Dear ImGui `ImGui::DragFloat2`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragFloat3` | `ImGui.DragFloat3()` | safe | Mirrors Dear ImGui `ImGui::DragFloat3`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragFloat4` | `ImGui.DragFloat4()` | safe | Mirrors Dear ImGui `ImGui::DragFloat4`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragFloatRange2` | `ImGui.DragFloatRange2()` | safe | Mirrors Dear ImGui `ImGui::DragFloatRange2`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragInt2` | `ImGui.DragInt2()` | safe | Mirrors Dear ImGui `ImGui::DragInt2`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragInt3` | `ImGui.DragInt3()` | safe | Mirrors Dear ImGui `ImGui::DragInt3`. See the Dear ImGui documentation for parameters and behaviour. |
| `DragInt4` | `ImGui.DragInt4()` | safe | Mirrors Dear ImGui `ImGui::DragInt4`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndChild` | `ImGui.EndChild()` | safe | Mirrors Dear ImGui `ImGui::EndChild`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndCombo` | `ImGui.EndCombo()` | safe | Mirrors Dear ImGui `ImGui::EndCombo`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndGroup` | `ImGui.EndGroup()` | safe | Mirrors Dear ImGui `ImGui::EndGroup`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndListBox` | `ImGui.EndListBox()` | safe | Mirrors Dear ImGui `ImGui::EndListBox`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndMainMenuBar` | `ImGui.EndMainMenuBar()` | safe | Mirrors Dear ImGui `ImGui::EndMainMenuBar`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndMenu` | `ImGui.EndMenu()` | safe | Mirrors Dear ImGui `ImGui::EndMenu`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndMenuBar` | `ImGui.EndMenuBar()` | safe | Mirrors Dear ImGui `ImGui::EndMenuBar`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndPopup` | `ImGui.EndPopup()` | safe | Mirrors Dear ImGui `ImGui::EndPopup`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndTabBar` | `ImGui.EndTabBar()` | safe | Mirrors Dear ImGui `ImGui::EndTabBar`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndTabItem` | `ImGui.EndTabItem()` | safe | Mirrors Dear ImGui `ImGui::EndTabItem`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndTable` | `ImGui.EndTable()` | safe | Mirrors Dear ImGui `ImGui::EndTable`. See the Dear ImGui documentation for parameters and behaviour. |
| `EndTooltip` | `ImGui.EndTooltip()` | safe | Mirrors Dear ImGui `ImGui::EndTooltip`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetBackgroundDrawList` | `ImGui.GetBackgroundDrawList()` | safe | Mirrors Dear ImGui `ImGui::GetBackgroundDrawList`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetClipboardText` | `ImGui.GetClipboardText()` | safe | Mirrors Dear ImGui `ImGui::GetClipboardText`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetContentRegionMax` | `ImGui.GetContentRegionMax()` | safe | Mirrors Dear ImGui `ImGui::GetContentRegionMax`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetCursorPos` | `ImGui.GetCursorPos()` | safe | Mirrors Dear ImGui `ImGui::GetCursorPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetCursorPosX` | `ImGui.GetCursorPosX()` | safe | Mirrors Dear ImGui `ImGui::GetCursorPosX`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetCursorPosY` | `ImGui.GetCursorPosY()` | safe | Mirrors Dear ImGui `ImGui::GetCursorPosY`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetCursorScreenPos` | `ImGui.GetCursorScreenPos()` | safe | Mirrors Dear ImGui `ImGui::GetCursorScreenPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetCursorStartPos` | `ImGui.GetCursorStartPos()` | safe | Mirrors Dear ImGui `ImGui::GetCursorStartPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetDrawListSharedData` | `ImGui.GetDrawListSharedData()` | safe | Mirrors Dear ImGui `ImGui::GetDrawListSharedData`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetFont` | `ImGui.GetFont()` | safe | Mirrors Dear ImGui `ImGui::GetFont`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetFontSize` | `ImGui.GetFontSize()` | safe | Mirrors Dear ImGui `ImGui::GetFontSize`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetForegroundDrawList` | `ImGui.GetForegroundDrawList()` | safe | Mirrors Dear ImGui `ImGui::GetForegroundDrawList`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetFrameCount` | `ImGui.GetFrameCount()` | safe | Mirrors Dear ImGui `ImGui::GetFrameCount`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetFrameHeight` | `ImGui.GetFrameHeight()` | safe | Mirrors Dear ImGui `ImGui::GetFrameHeight`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetFrameHeightWithSpacing` | `ImGui.GetFrameHeightWithSpacing()` | safe | Mirrors Dear ImGui `ImGui::GetFrameHeightWithSpacing`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetID` | `ImGui.GetID()` | safe | Mirrors Dear ImGui `ImGui::GetID`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetIO` | `ImGui.GetIO()` | safe | Mirrors Dear ImGui `ImGui::GetIO`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetItemRectMax` | `ImGui.GetItemRectMax()` | safe | Mirrors Dear ImGui `ImGui::GetItemRectMax`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetItemRectMin` | `ImGui.GetItemRectMin()` | safe | Mirrors Dear ImGui `ImGui::GetItemRectMin`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetItemRectSize` | `ImGui.GetItemRectSize()` | safe | Mirrors Dear ImGui `ImGui::GetItemRectSize`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetMainViewport` | `ImGui.GetMainViewport()` | safe | Mirrors Dear ImGui `ImGui::GetMainViewport`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetMouseCursor` | `ImGui.GetMouseCursor()` | safe | Mirrors Dear ImGui `ImGui::GetMouseCursor`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetMouseDelta` | `ImGui.GetMouseDelta()` | safe | Mirrors Dear ImGui `ImGui::GetMouseDelta`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetMouseDragDelta` | `ImGui.GetMouseDragDelta()` | safe | Mirrors Dear ImGui `ImGui::GetMouseDragDelta`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetMousePos` | `ImGui.GetMousePos()` | safe | Mirrors Dear ImGui `ImGui::GetMousePos`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetStyle` | `ImGui.GetStyle()` | safe | Mirrors Dear ImGui `ImGui::GetStyle`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetStyleColorVec4` | `ImGui.GetStyleColorVec4()` | safe | Mirrors Dear ImGui `ImGui::GetStyleColorVec4`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetTextLineHeight` | `ImGui.GetTextLineHeight()` | safe | Mirrors Dear ImGui `ImGui::GetTextLineHeight`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetTextLineHeightWithSpacing` | `ImGui.GetTextLineHeightWithSpacing()` | safe | Mirrors Dear ImGui `ImGui::GetTextLineHeightWithSpacing`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetTime` | `ImGui.GetTime()` | safe | Mirrors Dear ImGui `ImGui::GetTime`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowContentRegionMax` | `ImGui.GetWindowContentRegionMax()` | safe | Mirrors Dear ImGui `ImGui::GetWindowContentRegionMax`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowContentRegionMin` | `ImGui.GetWindowContentRegionMin()` | safe | Mirrors Dear ImGui `ImGui::GetWindowContentRegionMin`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowDrawList` | `ImGui.GetWindowDrawList()` | safe | Mirrors Dear ImGui `ImGui::GetWindowDrawList`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowHeight` | `ImGui.GetWindowHeight()` | safe | Mirrors Dear ImGui `ImGui::GetWindowHeight`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowPos` | `ImGui.GetWindowPos()` | safe | Mirrors Dear ImGui `ImGui::GetWindowPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowSize` | `ImGui.GetWindowSize()` | safe | Mirrors Dear ImGui `ImGui::GetWindowSize`. See the Dear ImGui documentation for parameters and behaviour. |
| `GetWindowWidth` | `ImGui.GetWindowWidth()` | safe | Mirrors Dear ImGui `ImGui::GetWindowWidth`. See the Dear ImGui documentation for parameters and behaviour. |
| `Image` | `ImGui.Image()` | safe | Mirrors Dear ImGui `ImGui::Image`. See the Dear ImGui documentation for parameters and behaviour. |
| `ImageButton` | `ImGui.ImageButton()` | safe | Mirrors Dear ImGui `ImGui::ImageButton`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputDouble` | `ImGui.InputDouble()` | safe | Mirrors Dear ImGui `ImGui::InputDouble`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputFloat2` | `ImGui.InputFloat2()` | safe | Mirrors Dear ImGui `ImGui::InputFloat2`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputFloat3` | `ImGui.InputFloat3()` | safe | Mirrors Dear ImGui `ImGui::InputFloat3`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputFloat4` | `ImGui.InputFloat4()` | safe | Mirrors Dear ImGui `ImGui::InputFloat4`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputInt2` | `ImGui.InputInt2()` | safe | Mirrors Dear ImGui `ImGui::InputInt2`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputInt3` | `ImGui.InputInt3()` | safe | Mirrors Dear ImGui `ImGui::InputInt3`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputInt4` | `ImGui.InputInt4()` | safe | Mirrors Dear ImGui `ImGui::InputInt4`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputScalar` | `ImGui.InputScalar()` | safe | Mirrors Dear ImGui `ImGui::InputScalar`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputTextMultiline` | `ImGui.InputTextMultiline()` | safe | Mirrors Dear ImGui `ImGui::InputTextMultiline`. See the Dear ImGui documentation for parameters and behaviour. |
| `InputTextWithHint` | `ImGui.InputTextWithHint()` | safe | Mirrors Dear ImGui `ImGui::InputTextWithHint`. See the Dear ImGui documentation for parameters and behaviour. |
| `InvisibleButton` | `ImGui.InvisibleButton()` | safe | Mirrors Dear ImGui `ImGui::InvisibleButton`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsAnyItemActive` | `ImGui.IsAnyItemActive()` | safe | Mirrors Dear ImGui `ImGui::IsAnyItemActive`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsAnyItemFocused` | `ImGui.IsAnyItemFocused()` | safe | Mirrors Dear ImGui `ImGui::IsAnyItemFocused`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsAnyItemHovered` | `ImGui.IsAnyItemHovered()` | safe | Mirrors Dear ImGui `ImGui::IsAnyItemHovered`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemActivated` | `ImGui.IsItemActivated()` | safe | Mirrors Dear ImGui `ImGui::IsItemActivated`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemActive` | `ImGui.IsItemActive()` | safe | Mirrors Dear ImGui `ImGui::IsItemActive`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemDeactivated` | `ImGui.IsItemDeactivated()` | safe | Mirrors Dear ImGui `ImGui::IsItemDeactivated`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemDeactivatedAfterEdit` | `ImGui.IsItemDeactivatedAfterEdit()` | safe | Mirrors Dear ImGui `ImGui::IsItemDeactivatedAfterEdit`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemEdited` | `ImGui.IsItemEdited()` | safe | Mirrors Dear ImGui `ImGui::IsItemEdited`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemFocused` | `ImGui.IsItemFocused()` | safe | Mirrors Dear ImGui `ImGui::IsItemFocused`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemToggledOpen` | `ImGui.IsItemToggledOpen()` | safe | Mirrors Dear ImGui `ImGui::IsItemToggledOpen`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsItemVisible` | `ImGui.IsItemVisible()` | safe | Mirrors Dear ImGui `ImGui::IsItemVisible`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsKeyDown` | `ImGui.IsKeyDown()` | safe | Mirrors Dear ImGui `ImGui::IsKeyDown`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsKeyPressed` | `ImGui.IsKeyPressed()` | safe | Mirrors Dear ImGui `ImGui::IsKeyPressed`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsKeyReleased` | `ImGui.IsKeyReleased()` | safe | Mirrors Dear ImGui `ImGui::IsKeyReleased`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsMouseClicked` | `ImGui.IsMouseClicked()` | safe | Mirrors Dear ImGui `ImGui::IsMouseClicked`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsMouseDoubleClicked` | `ImGui.IsMouseDoubleClicked()` | safe | Mirrors Dear ImGui `ImGui::IsMouseDoubleClicked`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsMouseDown` | `ImGui.IsMouseDown()` | safe | Mirrors Dear ImGui `ImGui::IsMouseDown`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsMouseHoveringRect` | `ImGui.IsMouseHoveringRect()` | safe | Mirrors Dear ImGui `ImGui::IsMouseHoveringRect`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsMouseReleased` | `ImGui.IsMouseReleased()` | safe | Mirrors Dear ImGui `ImGui::IsMouseReleased`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsPopupOpen` | `ImGui.IsPopupOpen()` | safe | Mirrors Dear ImGui `ImGui::IsPopupOpen`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsWindowAppearing` | `ImGui.IsWindowAppearing()` | safe | Mirrors Dear ImGui `ImGui::IsWindowAppearing`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsWindowCollapsed` | `ImGui.IsWindowCollapsed()` | safe | Mirrors Dear ImGui `ImGui::IsWindowCollapsed`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsWindowFocused` | `ImGui.IsWindowFocused()` | safe | Mirrors Dear ImGui `ImGui::IsWindowFocused`. See the Dear ImGui documentation for parameters and behaviour. |
| `IsWindowHovered` | `ImGui.IsWindowHovered()` | safe | Mirrors Dear ImGui `ImGui::IsWindowHovered`. See the Dear ImGui documentation for parameters and behaviour. |
| `ListBox` | `ImGui.ListBox()` | safe | Mirrors Dear ImGui `ImGui::ListBox`. See the Dear ImGui documentation for parameters and behaviour. |
| `MenuItem` | `ImGui.MenuItem()` | safe | Mirrors Dear ImGui `ImGui::MenuItem`. See the Dear ImGui documentation for parameters and behaviour. |
| `OpenPopup` | `ImGui.OpenPopup()` | safe | Mirrors Dear ImGui `ImGui::OpenPopup`. See the Dear ImGui documentation for parameters and behaviour. |
| `OpenPopupOnItemClick` | `ImGui.OpenPopupOnItemClick()` | safe | Mirrors Dear ImGui `ImGui::OpenPopupOnItemClick`. See the Dear ImGui documentation for parameters and behaviour. |
| `PopFont` | `ImGui.PopFont()` | safe | Mirrors Dear ImGui `ImGui::PopFont`. See the Dear ImGui documentation for parameters and behaviour. |
| `PopID` | `ImGui.PopID()` | safe | Mirrors Dear ImGui `ImGui::PopID`. See the Dear ImGui documentation for parameters and behaviour. |
| `PopItemWidth` | `ImGui.PopItemWidth()` | safe | Mirrors Dear ImGui `ImGui::PopItemWidth`. See the Dear ImGui documentation for parameters and behaviour. |
| `PopStyleColor` | `ImGui.PopStyleColor()` | safe | Mirrors Dear ImGui `ImGui::PopStyleColor`. See the Dear ImGui documentation for parameters and behaviour. |
| `PopStyleVar` | `ImGui.PopStyleVar()` | safe | Mirrors Dear ImGui `ImGui::PopStyleVar`. See the Dear ImGui documentation for parameters and behaviour. |
| `PopTextWrapPos` | `ImGui.PopTextWrapPos()` | safe | Mirrors Dear ImGui `ImGui::PopTextWrapPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `PushFont` | `ImGui.PushFont()` | safe | Mirrors Dear ImGui `ImGui::PushFont`. See the Dear ImGui documentation for parameters and behaviour. |
| `PushID` | `ImGui.PushID()` | safe | Mirrors Dear ImGui `ImGui::PushID`. See the Dear ImGui documentation for parameters and behaviour. |
| `PushItemWidth` | `ImGui.PushItemWidth()` | safe | Mirrors Dear ImGui `ImGui::PushItemWidth`. See the Dear ImGui documentation for parameters and behaviour. |
| `PushStyleColor` | `ImGui.PushStyleColor()` | safe | Mirrors Dear ImGui `ImGui::PushStyleColor`. See the Dear ImGui documentation for parameters and behaviour. |
| `PushStyleVar` | `ImGui.PushStyleVar()` | safe | Mirrors Dear ImGui `ImGui::PushStyleVar`. See the Dear ImGui documentation for parameters and behaviour. |
| `PushTextWrapPos` | `ImGui.PushTextWrapPos()` | safe | Mirrors Dear ImGui `ImGui::PushTextWrapPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `ResetMouseDragDelta` | `ImGui.ResetMouseDragDelta()` | safe | Mirrors Dear ImGui `ImGui::ResetMouseDragDelta`. See the Dear ImGui documentation for parameters and behaviour. |
| `Selectable` | `ImGui.Selectable()` | safe | Mirrors Dear ImGui `ImGui::Selectable`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetClipboardText` | `ImGui.SetClipboardText()` | safe | Mirrors Dear ImGui `ImGui::SetClipboardText`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetCursorPos` | `ImGui.SetCursorPos()` | safe | Mirrors Dear ImGui `ImGui::SetCursorPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetCursorPosX` | `ImGui.SetCursorPosX()` | safe | Mirrors Dear ImGui `ImGui::SetCursorPosX`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetCursorPosY` | `ImGui.SetCursorPosY()` | safe | Mirrors Dear ImGui `ImGui::SetCursorPosY`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetCursorScreenPos` | `ImGui.SetCursorScreenPos()` | safe | Mirrors Dear ImGui `ImGui::SetCursorScreenPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetItemAllowOverlap` | `ImGui.SetItemAllowOverlap()` | safe | Mirrors Dear ImGui `ImGui::SetItemAllowOverlap`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetItemDefaultFocus` | `ImGui.SetItemDefaultFocus()` | safe | Mirrors Dear ImGui `ImGui::SetItemDefaultFocus`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetItemTooltip` | `ImGui.SetItemTooltip()` | safe | Mirrors Dear ImGui `ImGui::SetItemTooltip`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetKeyboardFocusHere` | `ImGui.SetKeyboardFocusHere()` | safe | Mirrors Dear ImGui `ImGui::SetKeyboardFocusHere`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetMouseCursor` | `ImGui.SetMouseCursor()` | safe | Mirrors Dear ImGui `ImGui::SetMouseCursor`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetNextItemOpen` | `ImGui.SetNextItemOpen()` | safe | Mirrors Dear ImGui `ImGui::SetNextItemOpen`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetNextWindowBgAlpha` | `ImGui.SetNextWindowBgAlpha()` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowBgAlpha`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetNextWindowCollapsed` | `ImGui.SetNextWindowCollapsed()` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowCollapsed`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetNextWindowContentSize` | `ImGui.SetNextWindowContentSize()` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowContentSize`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetNextWindowDockID` | `ImGui.SetNextWindowDockID()` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowDockID`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetNextWindowFocus` | `ImGui.SetNextWindowFocus()` | safe | Mirrors Dear ImGui `ImGui::SetNextWindowFocus`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetTabItemClosed` | `ImGui.SetTabItemClosed()` | safe | Mirrors Dear ImGui `ImGui::SetTabItemClosed`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetWindowCollapsed` | `ImGui.SetWindowCollapsed()` | safe | Mirrors Dear ImGui `ImGui::SetWindowCollapsed`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetWindowFocus` | `ImGui.SetWindowFocus()` | safe | Mirrors Dear ImGui `ImGui::SetWindowFocus`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetWindowPos` | `ImGui.SetWindowPos()` | safe | Mirrors Dear ImGui `ImGui::SetWindowPos`. See the Dear ImGui documentation for parameters and behaviour. |
| `SetWindowSize` | `ImGui.SetWindowSize()` | safe | Mirrors Dear ImGui `ImGui::SetWindowSize`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderAngle` | `ImGui.SliderAngle()` | safe | Mirrors Dear ImGui `ImGui::SliderAngle`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderFloat2` | `ImGui.SliderFloat2()` | safe | Mirrors Dear ImGui `ImGui::SliderFloat2`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderFloat3` | `ImGui.SliderFloat3()` | safe | Mirrors Dear ImGui `ImGui::SliderFloat3`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderFloat4` | `ImGui.SliderFloat4()` | safe | Mirrors Dear ImGui `ImGui::SliderFloat4`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderInt2` | `ImGui.SliderInt2()` | safe | Mirrors Dear ImGui `ImGui::SliderInt2`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderInt3` | `ImGui.SliderInt3()` | safe | Mirrors Dear ImGui `ImGui::SliderInt3`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderInt4` | `ImGui.SliderInt4()` | safe | Mirrors Dear ImGui `ImGui::SliderInt4`. See the Dear ImGui documentation for parameters and behaviour. |
| `SliderScalar` | `ImGui.SliderScalar()` | safe | Mirrors Dear ImGui `ImGui::SliderScalar`. See the Dear ImGui documentation for parameters and behaviour. |
| `TabItemButton` | `ImGui.TabItemButton()` | safe | Mirrors Dear ImGui `ImGui::TabItemButton`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableAngledHeadersRow` | `ImGui.TableAngledHeadersRow()` | safe | Mirrors Dear ImGui `ImGui::TableAngledHeadersRow`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableGetColumnCount` | `ImGui.TableGetColumnCount()` | safe | Mirrors Dear ImGui `ImGui::TableGetColumnCount`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableGetColumnFlags` | `ImGui.TableGetColumnFlags()` | safe | Mirrors Dear ImGui `ImGui::TableGetColumnFlags`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableGetColumnIndex` | `ImGui.TableGetColumnIndex()` | safe | Mirrors Dear ImGui `ImGui::TableGetColumnIndex`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableGetColumnName` | `ImGui.TableGetColumnName()` | safe | Mirrors Dear ImGui `ImGui::TableGetColumnName`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableGetRowIndex` | `ImGui.TableGetRowIndex()` | safe | Mirrors Dear ImGui `ImGui::TableGetRowIndex`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableHeader` | `ImGui.TableHeader()` | safe | Mirrors Dear ImGui `ImGui::TableHeader`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableHeadersRow` | `ImGui.TableHeadersRow()` | safe | Mirrors Dear ImGui `ImGui::TableHeadersRow`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableNextColumn` | `ImGui.TableNextColumn()` | safe | Mirrors Dear ImGui `ImGui::TableNextColumn`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableNextRow` | `ImGui.TableNextRow()` | safe | Mirrors Dear ImGui `ImGui::TableNextRow`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableSetBgColor` | `ImGui.TableSetBgColor()` | safe | Mirrors Dear ImGui `ImGui::TableSetBgColor`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableSetColumnIndex` | `ImGui.TableSetColumnIndex()` | safe | Mirrors Dear ImGui `ImGui::TableSetColumnIndex`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableSetupColumn` | `ImGui.TableSetupColumn()` | safe | Mirrors Dear ImGui `ImGui::TableSetupColumn`. See the Dear ImGui documentation for parameters and behaviour. |
| `TableSetupScrollFreeze` | `ImGui.TableSetupScrollFreeze()` | safe | Mirrors Dear ImGui `ImGui::TableSetupScrollFreeze`. See the Dear ImGui documentation for parameters and behaviour. |
| `TextUnformatted` | `ImGui.TextUnformatted()` | safe | Mirrors Dear ImGui `ImGui::TextUnformatted`. See the Dear ImGui documentation for parameters and behaviour. |
| `TreeNode` | `ImGui.TreeNode()` | safe | Mirrors Dear ImGui `ImGui::TreeNode`. See the Dear ImGui documentation for parameters and behaviour. |
| `TreeNodeEx` | `ImGui.TreeNodeEx()` | safe | Mirrors Dear ImGui `ImGui::TreeNodeEx`. See the Dear ImGui documentation for parameters and behaviour. |
| `TreePop` | `ImGui.TreePop()` | safe | Mirrors Dear ImGui `ImGui::TreePop`. See the Dear ImGui documentation for parameters and behaviour. |
| `TreePush` | `ImGui.TreePush()` | safe | Mirrors Dear ImGui `ImGui::TreePush`. See the Dear ImGui documentation for parameters and behaviour. |
| `VSliderFloat` | `ImGui.VSliderFloat()` | safe | Mirrors Dear ImGui `ImGui::VSliderFloat`. See the Dear ImGui documentation for parameters and behaviour. |
| `VSliderInt` | `ImGui.VSliderInt()` | safe | Mirrors Dear ImGui `ImGui::VSliderInt`. See the Dear ImGui documentation for parameters and behaviour. |
| `ChildFlags` | `.ChildFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiChildFlags_` values (indexed as ImGui.ChildFlags.<Name>). See the Dear ImGui documentation. |
| `Col` | `.Col: table` | safe | Enum table mirroring Dear ImGui's `ImGuiCol_` values (indexed as ImGui.Col.<Name>). See the Dear ImGui documentation. |
| `ColorEditFlags` | `.ColorEditFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiColorEditFlags_` values (indexed as ImGui.ColorEditFlags.<Name>). See the Dear ImGui documentation. |
| `ComboFlags` | `.ComboFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiComboFlags_` values (indexed as ImGui.ComboFlags.<Name>). See the Dear ImGui documentation. |
| `Cond` | `.Cond: table` | safe | Enum table mirroring Dear ImGui's `ImGuiCond_` values (indexed as ImGui.Cond.<Name>). See the Dear ImGui documentation. |
| `Dir` | `.Dir: table` | safe | Enum table mirroring Dear ImGui's `ImGuiDir_` values (indexed as ImGui.Dir.<Name>). See the Dear ImGui documentation. |
| `DockNodeFlags` | `.DockNodeFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiDockNodeFlags_` values (indexed as ImGui.DockNodeFlags.<Name>). See the Dear ImGui documentation. |
| `DrawFlags` | `.DrawFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiDrawFlags_` values (indexed as ImGui.DrawFlags.<Name>). See the Dear ImGui documentation. |
| `FocusedFlags` | `.FocusedFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiFocusedFlags_` values (indexed as ImGui.FocusedFlags.<Name>). See the Dear ImGui documentation. |
| `HoveredFlags` | `.HoveredFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiHoveredFlags_` values (indexed as ImGui.HoveredFlags.<Name>). See the Dear ImGui documentation. |
| `InputTextFlags` | `.InputTextFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiInputTextFlags_` values (indexed as ImGui.InputTextFlags.<Name>). See the Dear ImGui documentation. |
| `Key` | `.Key: table` | safe | Enum table mirroring Dear ImGui's `ImGuiKey_` values (indexed as ImGui.Key.<Name>). See the Dear ImGui documentation. |
| `MouseButton` | `.MouseButton: table` | safe | Enum table mirroring Dear ImGui's `ImGuiMouseButton_` values (indexed as ImGui.MouseButton.<Name>). See the Dear ImGui documentation. |
| `PopupFlags` | `.PopupFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiPopupFlags_` values (indexed as ImGui.PopupFlags.<Name>). See the Dear ImGui documentation. |
| `SelectableFlags` | `.SelectableFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiSelectableFlags_` values (indexed as ImGui.SelectableFlags.<Name>). See the Dear ImGui documentation. |
| `SliderFlags` | `.SliderFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiSliderFlags_` values (indexed as ImGui.SliderFlags.<Name>). See the Dear ImGui documentation. |
| `SortDirection` | `.SortDirection: table` | safe | Enum table mirroring Dear ImGui's `ImGuiSortDirection_` values (indexed as ImGui.SortDirection.<Name>). See the Dear ImGui documentation. |
| `StyleVar` | `.StyleVar: table` | safe | Enum table mirroring Dear ImGui's `ImGuiStyleVar_` values (indexed as ImGui.StyleVar.<Name>). See the Dear ImGui documentation. |
| `TabBarFlags` | `.TabBarFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiTabBarFlags_` values (indexed as ImGui.TabBarFlags.<Name>). See the Dear ImGui documentation. |
| `TabItemFlags` | `.TabItemFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiTabItemFlags_` values (indexed as ImGui.TabItemFlags.<Name>). See the Dear ImGui documentation. |
| `TableColumnFlags` | `.TableColumnFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiTableColumnFlags_` values (indexed as ImGui.TableColumnFlags.<Name>). See the Dear ImGui documentation. |
| `TableFlags` | `.TableFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiTableFlags_` values (indexed as ImGui.TableFlags.<Name>). See the Dear ImGui documentation. |
| `TreeNodeFlags` | `.TreeNodeFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiTreeNodeFlags_` values (indexed as ImGui.TreeNodeFlags.<Name>). See the Dear ImGui documentation. |
| `WindowFlags` | `.WindowFlags: table` | safe | Enum table mirroring Dear ImGui's `ImGuiWindowFlags_` values (indexed as ImGui.WindowFlags.<Name>). See the Dear ImGui documentation. |

### Input

`table` · tier `safe` — Keyboard / mouse input queries.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `IsKeyDown` | `Input.IsKeyDown(vk: integer) -> boolean` | safe | True while the given virtual-key code is held and the game currently has keyboard input (menu closed, not typing). |
| `is_down` | `is_down` | safe | Alias of `Input.IsKeyDown` — true while the given virtual-key code is held in-game. |
| `is_key_down` | `is_key_down` | safe | Alias of `Input.IsKeyDown` — true while the given virtual-key code is held in-game. |
| `is_pressed` | `Input.is_pressed(vk: integer) -> boolean` | safe | True once when the key goes down. False while typing (see is_typing); is_down is unaffected. |
| `cursor_in_bounds` | `cursor_in_bounds` | safe | Returns true when the OS cursor's client-space position lies within the rectangle (x, y, w, h); false if the cursor position cannot be read. |
| `GetMousePos` | `Input.GetMousePos() -> table` | safe | Returns { x, y }. |
| `get_cursor_pos` | `get_cursor_pos` | safe | Alias of `Input.GetMousePos` — returns a table {x, y} with the OS cursor position in game-window client coordinates. |
| `GetMouseDelta` | `GetMouseDelta` | safe | Returns a table {dx, dy} with ImGui's per-frame mouse delta, or zeros before the overlay is initialized. |
| `mouse_wheel` | `Input.mouse_wheel() -> integer` | safe | Vertical mouse-wheel delta accumulated since the last call: 120 per notch (WHEEL_DELTA); touchpads give smaller values. +away from user / -toward. Consumes the accumulator; every read in one frame returns the same value, so a per-frame poll never double-counts a notch. |
| `mouse_wheel_h` | `Input.mouse_wheel_h() -> integer` | safe | Horizontal mouse-wheel delta since the last call (shift-scroll / tilt-wheel, WM_MOUSEHWHEEL): 120 per notch (WHEEL_DELTA); touchpads give smaller values. Same consume semantics as mouse_wheel(). |
| `is_menu_open` | `Input.is_menu_open() -> boolean` | safe | True while the Avalanche menu is open (uses fw::menu::open_intent). |
| `IsMenuOpen` | `Input.IsMenuOpen() -> boolean` | safe | True while the Avalanche overlay menu is open (reads the menu-open gate bit). |
| `menu_open` | `Input.menu_open() -> boolean` | safe | Alias of `Input.IsMenuOpen` — true while the Avalanche overlay menu is open. |
| `is_cursor_visible` | `Input.is_cursor_visible() -> boolean` | safe | True while the mouse cursor is being drawn (menu, modal, or game-side unlock). Backed by ImGuiIO::MouseDrawCursor at frame time. |
| `IsCursorVisible` | `Input.IsCursorVisible() -> boolean` | safe | True while ImGui is drawing the software cursor (reads the cursor-visible gate bit). |
| `cursor_visible` | `Input.cursor_visible() -> boolean` | safe | Alias of `Input.IsCursorVisible` — true while the overlay cursor is visible. |
| `is_ingame` | `Input.is_ingame() -> boolean` | safe | True when the menu is closed AND the cursor is locked -- i.e. the game has capture and the player is controlling their hero. |
| `IsInGame` | `Input.IsInGame() -> boolean` | safe | True when both the menu-open and cursor-visible gate bits are clear — i.e. keyboard/mouse input is going to the game. |
| `in_game` | `Input.in_game() -> boolean` | safe | Alias of `Input.IsInGame` — true when input is going to the game (menu closed and cursor hidden). |
| `is_typing` | `Input.is_typing() -> boolean` | safe | True while someone is typing: the game's chat or console takes text, or a text field of the menu or a Lua window has keyboard focus. Sampled once per rendered frame. Menu navigation alone does not count. |
| `IsTyping` | `Input.IsTyping() -> boolean` | safe | Same function as is_typing. |
| `typing` | `Input.typing() -> boolean` | safe | Same function as is_typing. |

### Keys

`table` · tier `safe` — Key-code constants: the Windows VK of every key a bind can use, left and right modifiers apart. enums.VKey is the same table.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `MOUSE1` | `.MOUSE1: integer` | safe | Left mouse button. |
| `MOUSE2` | `.MOUSE2: integer` | safe | Right mouse button. |
| `MOUSE3` | `.MOUSE3: integer` | safe | Middle mouse button. |
| `MOUSE4` | `.MOUSE4: integer` | safe | Mouse button 4 (XButton1 / back). |
| `MOUSE5` | `.MOUSE5: integer` | safe | Mouse button 5 (XButton2 / forward). |
| `SHIFT` | `.SHIFT: integer` | safe | Shift. |
| `CTRL` | `.CTRL: integer` | safe | Ctrl. |
| `ALT` | `.ALT: integer` | safe | Alt. |
| `SPACE` | `.SPACE: integer` | safe | Space. |
| `TAB` | `.TAB: integer` | safe | Tab. |
| `ENTER` | `.ENTER: integer` | safe | Enter. |
| `ESC` | `.ESC: integer` | safe | Esc. |
| `F1` | `.F1: integer` | safe | F1. |
| `F2` | `.F2: integer` | safe | F2. |
| `F3` | `.F3: integer` | safe | F3. |
| `F4` | `.F4: integer` | safe | F4. |
| `F5` | `.F5: integer` | safe | F5. |
| `F6` | `.F6: integer` | safe | F6. |
| `F7` | `.F7: integer` | safe | F7. |
| `F8` | `.F8: integer` | safe | F8. |
| `F9` | `.F9: integer` | safe | F9. |
| `F10` | `.F10: integer` | safe | F10. |
| `F11` | `.F11: integer` | safe | F11. |
| `F12` | `.F12: integer` | safe | F12. |
| `A` | `.A: integer` | safe | A key. |
| `B` | `.B: integer` | safe | B key. |
| `C` | `.C: integer` | safe | C key. |
| `D` | `.D: integer` | safe | D key. |
| `E` | `.E: integer` | safe | E key. |
| `F` | `.F: integer` | safe | F key. |
| `G` | `.G: integer` | safe | G key. |
| `H` | `.H: integer` | safe | H key. |
| `I` | `.I: integer` | safe | I key. |
| `J` | `.J: integer` | safe | J key. |
| `K` | `.K: integer` | safe | K key. |
| `L` | `.L: integer` | safe | L key. |
| `M` | `.M: integer` | safe | M key. |
| `N` | `.N: integer` | safe | N key. |
| `O` | `.O: integer` | safe | O key. |
| `P` | `.P: integer` | safe | P key. |
| `Q` | `.Q: integer` | safe | Q key. |
| `R` | `.R: integer` | safe | R key. |
| `S` | `.S: integer` | safe | S key. |
| `T` | `.T: integer` | safe | T key. |
| `U` | `.U: integer` | safe | U key. |
| `V` | `.V: integer` | safe | V key. |
| `W` | `.W: integer` | safe | W key. |
| `X` | `.X: integer` | safe | X key. |
| `Y` | `.Y: integer` | safe | Y key. |
| `Z` | `.Z: integer` | safe | Z key. |
| `0` | `.0: integer` | safe | 0 key. |
| `1` | `.1: integer` | safe | 1 key. |
| `2` | `.2: integer` | safe | 2 key. |
| `3` | `.3: integer` | safe | 3 key. |
| `4` | `.4: integer` | safe | 4 key. |
| `5` | `.5: integer` | safe | 5 key. |
| `6` | `.6: integer` | safe | 6 key. |
| `7` | `.7: integer` | safe | 7 key. |
| `8` | `.8: integer` | safe | 8 key. |
| `9` | `.9: integer` | safe | 9 key. |
| `LSHIFT` | `.LSHIFT: integer` | safe | Left Shift. |
| `RSHIFT` | `.RSHIFT: integer` | safe | Right Shift. |
| `LCTRL` | `.LCTRL: integer` | safe | Left Ctrl. |
| `RCTRL` | `.RCTRL: integer` | safe | Right Ctrl. |
| `LALT` | `.LALT: integer` | safe | Left Alt. |
| `RALT` | `.RALT: integer` | safe | Right Alt (AltGr). |
| `LWIN` | `.LWIN: integer` | safe | Left Windows key. |
| `RWIN` | `.RWIN: integer` | safe | Right Windows key. |
| `APPS` | `.APPS: integer` | safe | Menu (application) key. |
| `BACKSPACE` | `.BACKSPACE: integer` | safe | Backspace. |
| `INSERT` | `.INSERT: integer` | safe | Insert. |
| `DELETE` | `.DELETE: integer` | safe | Delete. |
| `HOME` | `.HOME: integer` | safe | Home. |
| `END` | `.END: integer` | safe | End. |
| `PAGEUP` | `.PAGEUP: integer` | safe | Page Up. |
| `PAGEDOWN` | `.PAGEDOWN: integer` | safe | Page Down. |
| `LEFT` | `.LEFT: integer` | safe | Left arrow. |
| `RIGHT` | `.RIGHT: integer` | safe | Right arrow. |
| `UP` | `.UP: integer` | safe | Up arrow. |
| `DOWN` | `.DOWN: integer` | safe | Down arrow. |
| `CAPSLOCK` | `.CAPSLOCK: integer` | safe | Caps Lock. |
| `SCROLLLOCK` | `.SCROLLLOCK: integer` | safe | Scroll Lock. |
| `NUMLOCK` | `.NUMLOCK: integer` | safe | Num Lock. |
| `PRINTSCREEN` | `.PRINTSCREEN: integer` | safe | Print Screen. |
| `PAUSE` | `.PAUSE: integer` | safe | Pause/Break. |
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
| `F13` | `.F13: integer` | safe | F13. |
| `F14` | `.F14: integer` | safe | F14. |
| `F15` | `.F15: integer` | safe | F15. |
| `F16` | `.F16: integer` | safe | F16. |
| `F17` | `.F17: integer` | safe | F17. |
| `F18` | `.F18: integer` | safe | F18. |
| `F19` | `.F19: integer` | safe | F19. |
| `F20` | `.F20: integer` | safe | F20. |
| `F21` | `.F21: integer` | safe | F21. |
| `F22` | `.F22: integer` | safe | F22. |
| `F23` | `.F23: integer` | safe | F23. |
| `F24` | `.F24: integer` | safe | F24. |

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
| `local_pawn` | `entity_list.local_pawn() -> PlayerPawn\|nil` | safe | Returns the local player's pawn (av::ef::LocalPawn), or nil when there is no local pawn. |
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
| `all_players` | `entity_list.all_players() -> table` | safe | Alias of `entity_list.players`. |
| `local_hero` | `entity_list.local_hero() -> PlayerPawn` | safe | Alias of `entity_list.local_pawn`. |
| `local_index` | `entity_list.local_index() -> integer` | safe | Returns the local pawn's entity index, or -1 when there is no local pawn. |
| `by_class_name_partial` | `entity_list.by_class_name_partial(prefix: string) -> table` | safe | Returns an array of live entities whose class binding name starts with `prefix`; empty when the prefix is empty, capped at 1024 entries. |
| `by_owner` | `entity_list.by_owner(owner: Entity) -> table` | safe | Returns an array of up to 1024 live entities whose owner handle points to `owner`, excluding `owner` itself. |
| `find_by_partial` | `entity_list.find_by_partial(prefix: string) -> table` | safe | Alias of `entity_list.by_class_name_partial`; returns live entities whose binding class name starts with the prefix (capped at 1024). |
| `get_handle` | `entity_list.get_handle(entity: any) -> integer` | safe | Returns the `m_Index` of the entity's `EHandle`, or 0 when the argument does not resolve to a live entity. |
| `is_valid` | `entity_list.is_valid(ent: Entity\|integer) -> boolean` | safe | True when the argument resolves to a live entity record. |
| `iterate` | `entity_list.iterate() -> table` | safe | Returns an array of up to 4096 live `C_BaseEntity` entries from the current entity view; bails out early if the view becomes unstable. |

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
| `set_scope` | `storage.set_scope(scope: string, key: string, value: any) -> boolean` | safe | Writes `value` into the `scope:key` slot of the global KV store; only trusted callers may use it, and setting nil erases the entry. Returns true on success. |
| `size` | `storage.size() -> integer` | safe | Returns the number of bytes currently used by the calling script's storage bucket; 0 if nothing has been written. |
| `sync_from_disk` | `storage.sync_from_disk() -> boolean` | safe | Alias of `storage.load`. |
| `clear` | `storage.clear()` | safe | Removes every key owned by the calling script from the key/value store and resets its byte accounting to zero. |
| `count` | `storage.count() -> integer` | safe | Returns the number of persisted keys owned by the calling script. |
| `create_bucket` | `storage.create_bucket(name: string) -> boolean` | safe | Registers `name` as a persisted bucket for the caller script; returns false if `name` is empty, true otherwise. |
| `delete` | `storage.delete(key: string) -> boolean` | safe | Removes the key from the calling script's storage namespace; returns false if the key is missing or arg 1 is not a string, true after a successful erase. |
| `drop_bucket` | `storage.drop_bucket(name: string) -> boolean` | safe | Removes every key in the named bucket owned by the calling script and detaches the bucket; returns false for an empty name, true otherwise. |
| `get_scope` | `storage.get_scope(scope: string, key: string) -> any` | safe | Reads the `scope:key` entry from the shared store. Non-trusted callers may only read their own scope; mismatched scopes yield nil. |
| `has` | `storage.has(key: string) -> boolean` | safe | Returns true if `key` exists in this script's storage namespace; false when `key` is not a string or no entry is present. |
| `keys` | `storage.keys() -> table` | safe | Returns an array of keys owned by the calling script (the shared bucket prefix is stripped). |
| `list_buckets` | `storage.list_buckets() -> table` | safe | Returns an array of bucket names created by the calling script via storage.create_bucket. |
| `persist` | `storage.persist() -> boolean` | safe | Alias of `storage.save`: serialises the caller script's storage bucket to JSON and writes it to the script's on-disk storage file, returning true on success and false if the path could not be built or the write failed. |
| `remove` | `storage.remove(key: string) -> boolean` | safe | Alias of `storage.delete`. |

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
| `UnitsToMeters` | `Math.UnitsToMeters(u: number) -> number` | safe | Converts engine units to meters (multiplies by 0.0254). |
| `MetersToUnits` | `Math.MetersToUnits(m: number) -> number` | safe | Converts meters to engine units (divides by 0.0254); matches the engine's own round-trip bit-exactly. |
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
| `Deg2Rad` | `Math.Deg2Rad(d: number) -> number` | safe | Converts degrees to radians. |
| `Rad2Deg` | `Math.Rad2Deg(r: number) -> number` | safe | Converts radians to degrees. |
| `InRange` | `Math.InRange(x: number, lo: number, hi: number) -> boolean` | safe | True when `x` lies in `[lo, hi]` (inclusive). |
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
| `angle_diff` | `Math.angle_diff(a: number, b: number) -> number` | safe | Alias of `amath.angle_diff` — returns `a - b` normalised to the (-180, 180] yaw range. |
| `fov_between` | `Math.fov_between(ex: number, ey: number, ez: number, fx: number, fy: number, fz: number, tx: number, ty: number, tz: number) -> number` | safe | Angle in degrees between a view forward vector and the direction from eye to target; returns 0 when the two points coincide. |
| `sign` | `Math.sign(v: number) -> number` | safe | Alias of `amath.sign` — returns -1, 0 or 1 for the sign of `v`. |
| `angles_to_forward` | `Math.angles_to_forward(pitch: number, yaw: number) -> table` | safe | Returns a {x, y, z} table for the forward vector of a QAngle(pitch, yaw, 0) via `AngleVectors`. |
| `fract` | `Math.fract(x: number) -> number` | safe | Returns the fractional part `x - floor(x)`. |
| `smoothstep` | `Math.smoothstep(edge0: number, edge1: number, x: number) -> number` | safe | Hermite smoothstep: 0 when `x` is at/below `edge0`, 1 at/above `edge1`, cubic interpolation in between; returns 0 when the edges are equal. |
| `approach` | `Math.approach(cur: number, target: number, step: number) -> number` | safe | Moves `cur` toward `target` by at most `step` and returns the result; stops exactly at `target` when within one step. |
| `in_range` | `Math.in_range(x: number, lo: number, hi: number) -> boolean` | safe | Returns true when `lo <= x <= hi`. |
| `snap` | `Math.snap(x: number, step: number) -> number` | safe | Rounds `x` to the nearest multiple of `step`; returns `x` unchanged when `step` is zero. |
| `ceil` | `Math.ceil(x: number) -> number` | safe | Returns `ceilf(x)` as a float. |
| `length3` | `Math.length3(x: number, y: number, z: number) -> number` | safe | Euclidean length of the 3-component vector: `sqrt(x*x + y*y + z*z)`. |
| `wrap` | `Math.wrap(x: number, lo: number, hi: number) -> number` | safe | Wraps `x` into the half-open range `[lo, hi)`; returns `lo` if `hi <= lo`. |
| `clamp` | `Math.clamp(x: number, lo: number, hi: number) -> number` | safe | Clamps x to the inclusive range [lo, hi]. |
| `lerp` | `Math.lerp(a: number, b: number, t: number) -> number` | safe | Linear interpolation a + (b - a) * t. |
| `CalcQAngle` | `Math.CalcQAngle(from: Vector3, to: Vector3) -> QAngle` | safe | Returns the QAngle that aims from the point from toward to. |
| `cross3` | `Math.cross3(ax: number, ay: number, az: number, bx: number, by: number, bz: number) -> table` | safe | Returns the 3-D cross product of (ax,ay,az) and (bx,by,bz) as a fresh table with x, y, z fields. |
| `max` | `Math.max(a: number, b: number) -> number` | safe | Returns the larger of two floats. |
| `deg2rad` | `Math.deg2rad(d: number) -> number` | safe | Converts degrees to radians. |
| `max3` | `Math.max3(a: number, b: number, c: number) -> number` | safe | Returns the largest of three numbers. |
| `Abs` | `Math.Abs(x: number) -> number` | safe | Absolute value of `x`. |
| `dot3` | `Math.dot3(ax: number, ay: number, az: number, bx: number, by: number, bz: number) -> number` | safe | Dot product of the two 3-component vectors supplied as six scalars. |
| `min` | `Math.min(a: number, b: number) -> number` | safe | Smaller of `a` and `b`. |
| `Ceil` | `Math.Ceil(x: number) -> number` | safe | Alias of `amath.ceil` (returns ceilf(x)). |
| `ease_in_cubic` | `Math.ease_in_cubic(t: number) -> number` | safe | Alias of `amath.ease_in_cubic` (returns t*t*t). |
| `min3` | `Math.min3(a: number, b: number, c: number) -> number` | safe | Alias of `amath.min3` (minimum of three values). |
| `Floor` | `Math.Floor(x: number) -> number` | safe | Returns `floorf(x)`. |
| `ease_in_out_cubic` | `Math.ease_in_out_cubic(t: number) -> number` | safe | Cubic ease-in-out: `4t^3` below 0.5, `1 - ((-2t + 2)^3) / 2` above. |
| `normalize3` | `Math.normalize3(x: number, y: number, z: number) -> table` | safe | Returns a `{x, y, z}` table of the unit vector; all three fields are zero when the input length is below ~1e-6. |
| `Fract` | `Math.Fract(x: number) -> number` | safe | Alias of `Math.fract`. |
| `ease_in_out_quad` | `Math.ease_in_out_quad(t: number) -> number` | safe | Quadratic ease-in-out on t in [0,1]: 2t² below 0.5, else 1 - 2(1-t)². |
| `normalize_yaw` | `Math.normalize_yaw(yaw: number) -> number` | safe | Wraps a yaw into the [-180, 180] range via the engine's angle-normalize. |
| `Max` | `Math.Max(a: number, b: number) -> number` | safe | Alias of `amath.max`; returns the greater of `a` and `b`. |
| `ease_in_quad` | `Math.ease_in_quad(t: number) -> number` | safe | Quadratic ease-in: returns `t * t`. |
| `rad2deg` | `Math.rad2deg(r: number) -> number` | safe | Converts radians to degrees (multiplies by ~57.29578). |
| `Min` | `Math.Min(a: number, b: number) -> number` | safe | Returns the smaller of a and b. |
| `ease_out_cubic` | `Math.ease_out_cubic(t: number) -> number` | safe | Cubic ease-out: 1 - (1 - t)^3. |
| `remap` | `Math.remap(v: number, srcLo: number, srcHi: number, dstLo: number, dstHi: number) -> number` | safe | Linearly remaps v from [srcLo, srcHi] onto [dstLo, dstHi]; returns dstLo when srcHi equals srcLo and does not clamp outside the source range. |
| `Saturate` | `Math.Saturate(x: number) -> number` | safe | Clamps x into [0, 1]. |
| `ease_out_quad` | `Math.ease_out_quad(t: number) -> number` | safe | Quadratic ease-out: 1 - (1 - t)^2. |
| `remap_clamped` | `Math.remap_clamped(v: number, src_lo: number, src_hi: number, dst_lo: number, dst_hi: number) -> number` | safe | Linearly remaps v from [src_lo, src_hi] to [dst_lo, dst_hi]; result is clamped to the destination range. Returns dst_lo when src_lo == src_hi. |
| `Wrap` | `Math.Wrap(x: number, lo: number, hi: number) -> number` | safe | Alias of `Math.wrap`: wraps x into the half-open range [lo, hi) via floor-modulo; returns lo when hi <= lo. |
| `floor` | `Math.floor(x: number) -> number` | safe | Returns floor(x) as a float (wraps C `floorf`). |
| `round` | `Math.round(x: number) -> number` | safe | Rounds x to the nearest integer value using half-away-from-zero rounding. |
| `abs` | `Math.abs(x: number) -> number` | safe | Absolute value of x. |
| `forward_to_angles` | `Math.forward_to_angles(fx: number, fy: number, fz: number) -> number,number,number` | safe | Alias of `amath.ForwardToAngles` — converts a forward vector to pitch/yaw/roll. |
| `saturate` | `Math.saturate(x: number) -> number` | safe | Clamps x to [0, 1]. |

### Game

`table` · tier `safe` — Game-state helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `GetLocalPlayer` | `Game.GetLocalPlayer() -> PlayerPawn\|nil` | safe | Local player pawn (nil if not up yet). |
| `GetAllPlayers` | `Game.GetAllPlayers() -> PlayerPawn[]` | safe | 1-indexed array of live CITADEL_PLAYER_PAWN entities. |
| `GetPlayerByIndex` | `Game.GetPlayerByIndex(index: integer) -> PlayerPawn\|nil` | safe | Same function as entity_list.by_index. |
| `IsInGame` | `Game.IsInGame() -> boolean` | safe | IVEngineToClient::IsInGame(). |
| `ForEachPlayer` | `Game.ForEachPlayer(fn: function)` | safe | Iterates every live player pawn and invokes fn(pawn) for each; stops on an invalid pcall result or a mid-walk entity-table change. |
| `GetLocalController` | `Game.GetLocalController() -> PlayerController\|nil` | safe | Returns the local player's controller via `av::ef::LocalController()`, or nil when no local controller is known. |
| `GetPlayerCount` | `Game.GetPlayerCount() -> integer` | safe | Number of live player-pawn entity records in the current frame snapshot. |
| `get_all_players` | `Game.get_all_players() -> table` | safe | Alias of `Game.GetAllPlayers`; returns an array of live Citadel player pawns from the entity view. |
| `get_local_pawn` | `Game.get_local_pawn() -> PlayerPawn\|nil` | safe | Alias of `Game.GetLocalPlayer`. |
| `get_player_count` | `Game.get_player_count() -> integer` | safe | Alias of `Game.GetPlayerCount`: returns the current count of player pawns in the entity view. |
| `is_in_game` | `Game.is_in_game() -> boolean` | safe | Alias of `Game.IsInGame`. |

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
| `RunFastMouseAssist` | `Combat.RunFastMouseAssist(target_pos: Vector3) -> boolean` | safe | Runs the mouse-assist tick with preset speed=3, deadzone=0.05 and max-per-frame=200; returns false when the game is not focused. |
| `RunMouseAssist` | `Combat.RunMouseAssist(targetPos: Vector3, speed: number?, deadzone: number?, maxPerFrame: number?) -> boolean` | safe | Drives the mouse-assist controller toward `targetPos` with the given speed (default 10), deadzone (default 0.1) and per-frame cap (default 25); returns false immediately when the game isn't focused. |
| `WhyNotRunning` | `Combat.WhyNotRunning() -> integer` | safe | Returns the integer reason code (0 when combat features are allowed to run) for why combat is currently gated. |

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
| `dump` | `utils.dump(v: any) -> string` | safe | Alias of `utils.pretty_print` — flat textual dump of a table (keys and `tostring` values) or any other value. |
| `shallow_copy` | `utils.shallow_copy(t: table) -> table` | safe | Returns a new table with the same top-level key/value pairs; non-table inputs are returned unchanged. |
| `dump_stack` | `utils.dump_stack() -> table` | safe | Returns an array of frame tables walking the Lua call stack from the current frame outward; each entry has `source`, `line`, `name`, `what`. |
| `sign` | `utils.sign(x: number) -> integer` | safe | Returns 1 for positive input, -1 for negative input, 0 for zero. |
| `set_midboss_panel` | `utils.set_midboss_panel(mode: integer) -> nil` | safe | Sets the midboss HUD panel mode (clamped to the Default..Hide range), reclaiming ownership for the calling script and arming the applier when the mode changes. |
| `hash` | `utils.hash(s: string) -> integer` | safe | Returns the FNV1a-64 hash of `s` masked to a positive 63-bit integer. |
| `stack` | `utils.stack() -> table` | safe | Returns a new empty stack table with a `_top` counter initialised to 0. |
| `hash_seed` | `utils.hash_seed() -> integer` | safe | Returns the process-wide, lazy-initialized 63-bit hash seed drawn from current time on first call. |
| `try_call` | `utils.try_call(fn: fun(...), ...: any) -> boolean, any` | safe | Pcall-guards `fn(...)`; returns `(true, result)` on success or `(false, error_message)` on error / non-function. |
| `hexdump` | `utils.hexdump(s: string) -> string` | safe | Returns s as a lowercase hex string with no separators. |
| `unwrap` | `utils.unwrap(v: any, msg: string?) -> any` | safe | Returns v when it is not nil; raises a Lua error with msg (default "unwrap on nil") otherwise. |
| `is_boolean` | `utils.is_boolean(v: any) -> boolean` | safe | Returns true when the first argument is a Lua boolean. |
| `values_of` | `utils.values_of(t: table) -> table` | safe | Returns a new array table containing the values of t in iteration order (empty table if t is not a table). |
| `is_minimap_visible` | `utils.is_minimap_visible() -> boolean` | safe | Returns true when the HUD minimap is currently flagged visible (av::world::MinimapVisibility() == 1). |
| `assert` | `utils.assert(cond: any, msg: string\|nil) -> any` | safe | If `cond` is truthy returns it; otherwise raises a Lua error with `msg` (default `"assertion failed"`). |
| `is_function` | `utils.is_function(v: any) -> boolean` | safe | Returns true when `v` is a Lua function. |
| `time_delta` | `utils.time_delta(t0: number) -> number` | safe | Returns the current game time minus `t0`. |
| `avg_of` | `utils.avg_of(...: number) -> number` | safe | Arithmetic mean of all numeric varargs; returns 0 when called with no arguments. |
| `is_nil` | `utils.is_nil(v: any) -> boolean` | safe | True if the first argument's Lua type is `nil`. |
| `bit_and` | `utils.bit_and(a: integer, b: integer) -> integer` | safe | Returns the bitwise AND of two integers. |
| `is_number` | `utils.is_number(v: any) -> boolean` | safe | True when arg 1 has Lua type LUA_TNUMBER. |
| `bit_not` | `utils.bit_not(x: integer) -> integer` | safe | Bitwise NOT of the integer argument. |
| `is_string` | `utils.is_string(v: any) -> boolean` | safe | True if the first argument is a Lua string. |
| `bit_or` | `utils.bit_or(a: integer, b: integer) -> integer` | safe | Bitwise OR of two integers. |
| `is_table` | `utils.is_table(v: any) -> boolean` | safe | True when the argument's Lua type is table. |
| `bit_shl` | `utils.bit_shl(a: integer, b: integer) -> integer` | safe | Returns `a << (b & 63)`. |
| `keys_of` | `utils.keys_of(t: table) -> table` | safe | Returns an array of `t`'s keys in iteration order; empty when `t` is not a table. |
| `bit_shr` | `utils.bit_shr(v: integer, count: integer) -> integer` | safe | Unsigned 64-bit right shift of v by (count & 63). |
| `max_of` | `utils.max_of(...: number) -> number\|nil` | safe | Returns the maximum of its numeric arguments; nil when called with no arguments. |
| `bit_test` | `utils.bit_test(v: integer, b: integer) -> boolean` | safe | Returns true if bit b (masked to 0..63) of integer v is set. |
| `min_of` | `utils.min_of(...: number) -> number\|nil` | safe | Returns the smallest of the number arguments; nil when called with none. |
| `bit_xor` | `utils.bit_xor(a: integer, b: integer) -> integer` | safe | Returns the bitwise XOR of a and b. |
| `pretty_print` | `utils.pretty_print(v: any) -> string` | safe | Returns a single-line string form of v; for tables it emits `{key=value, ...}` with each entry's value run through `luaL_tolstring`, and for non-tables it returns `luaL_tolstring(v)`. |
| `deep_copy` | `utils.deep_copy(t: any) -> any` | safe | Returns a deep clone of a table (cycle-safe via a seen set and bounded depth); non-tables are returned unchanged. |
| `queue` | `utils.queue() -> table` | safe | Creates an empty FIFO queue table with `_head=1` and `_tail=0`. |

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
| `get_viewport` | `draw.get_viewport() -> table` | safe | Returns `{ width, height }` for the current overlay viewport. |
| `gradient_rect` | `draw.gradient_rect(x1: number, y1: number, x2: number, y2: number, cA: Color, cB: Color, vertical: boolean\|nil) -> nil` | safe | Fills the rect defined by two corners with a two-color gradient (vertical by default when the flag is omitted); counts as one Draw-API rect call. No-op outside a render context. |
| `is_point_in_box` | `draw.is_point_in_box(px: number, py: number, x1: number, y1: number, x2: number, y2: number) -> boolean` | safe | Returns true when the point `(px, py)` lies inside the axis-aligned box `(x1,y1)-(x2,y2)`. |
| `polygon` | `draw.polygon(points: table, color: Color?, filled: boolean?, thickness: number?)` | safe | Draws a polygon from an array of {x,y} points; `filled` defaults to false, `thickness` to 1. |
| `rounded_rect` | `draw.rounded_rect(x1: number, y1: number, x2: number, y2: number, rounding: number, color: Color?, filled: boolean?, thickness: number?)` | safe | Draws a rounded rectangle; color defaults to white, filled defaults to true, and thickness defaults to 1. |
| `arrow_3d` | `draw.arrow_3d(fx: number, fy: number, fz: number, tx: number, ty: number, tz: number, color: Color\|nil, thickness: number\|nil) -> nil` | safe | Queues a 3-D arrow from (fx,fy,fz) to (tx,ty,tz) at the given color (defaults to white) and line thickness (defaults to 1). |
| `color` | `draw.color(r: integer, g: integer, b: integer, a: integer\|nil) -> table` | safe | Builds a {r,g,b,a} color table with each channel clamped to 0-255; a defaults to 255. |
| `shadow` | `draw.shadow(x1: number, y1: number, x2: number, y2: number, color: Color\|nil, alpha: integer\|nil, distance: number\|nil) -> nil` | safe | Draws a filled rectangle offset by distance (default 2) in both axes, using color (default white) with its alpha overridden to alpha (default 90). |
| `arrow_3d_v` | `draw.arrow_3d_v(from: Vector3, to: Vector3, color: Color\|nil, thickness: number\|nil) -> nil` | safe | Queues a 3D arrow from `from` to `to`; color defaults to white and `thickness` to 1. |
| `color_hex` | `draw.color_hex(hex: integer, alpha: integer\|nil) -> table` | safe | Builds a `{r,g,b,a}` color table from a 24-bit packed `0xRRGGBB` integer; alpha defaults to 255. |
| `triangle` | `draw.triangle(ax: number, ay: number, bx: number, by: number, cx: number, cy: number, color: Color\|nil, filled: boolean\|nil, thickness: number\|nil) -> nil` | safe | Queues a 2D triangle; color defaults to white, `filled` to false, `thickness` to 1. |
| `box_3d` | `draw.box_3d(x1: number, y1: number, z1: number, x2: number, y2: number, z2: number, color: Color\|nil, thickness: number\|nil)` | safe | Draws a wireframe 3D box between the two world-space corners; `color` defaults to white and `thickness` to 1. |
| `color_lerp` | `draw.color_lerp(a: Color, b: Color, t: number) -> table` | safe | Returns a `{r, g, b, a}` table whose channels are linearly interpolated between `a` and `b` with `t` clamped to `[0, 1]`. |
| `box_3d_v` | `draw.box_3d_v(mins: Vector3, maxs: Vector3, color: Color?, thickness: number?) -> nil` | safe | Enqueues a 3D wireframe box between the two world-space corners; color defaults to white, thickness to 1. |
| `color_with_alpha` | `draw.color_with_alpha(c: Color, alpha: integer) -> table` | safe | Returns a new {r,g,b,a} table copying c's RGB and replacing alpha with the clamped byte value. |
| `circle_3d_v` | `draw.circle_3d_v(center: Vector3, radius: number, color: Color?) -> nil` | safe | Submits a 3D circle at the given world-space center and radius, defaulting to white when no color is passed. |
| `filled_circle` | `draw.filled_circle(cx: number, cy: number, radius: number, color: Color?) -> nil` | safe | Draws a filled 2D circle at (`cx`, `cy`) with the given radius; defaults to white when no color is supplied. |
| `line_3d_v` | `draw.line_3d_v(from: Vector3, to: Vector3, color: Color?, thickness: number?)` | safe | Vector-form of `draw.line_3d`: queues a world-space line from `from` to `to`. Color defaults to white and thickness to 1. |
| `filled_polygon` | `draw.filled_polygon(points: table, color: Color?)` | safe | Queues a filled polygon from an array of {x,y} points; color defaults to white. |
| `sphere_3d` | `draw.sphere_3d(x: number, y: number, z: number, radius: number, color: Color\|nil)` | safe | Draws a 3D sphere at `(x,y,z)` with the given radius; `color` defaults to white. |
| `filled_rect` | `draw.filled_rect(x1: number, y1: number, x2: number, y2: number, color: Color\|nil)` | safe | Fills the rectangle `(x1,y1)-(x2,y2)`; `color` defaults to white. |
| `sphere_3d_v` | `draw.sphere_3d_v(center: Vector3, radius: number, color: Color?) -> nil` | safe | Queues a world-space wire sphere at `center`; defaults to white when color is omitted. |
| `filled_triangle` | `draw.filled_triangle(ax: number, ay: number, bx: number, by: number, cx: number, cy: number, color: Color?) -> nil` | safe | Draws a filled 2D triangle (defaults to white when color is omitted). |
| `world_to_screen` | `draw.world_to_screen(wx: number, wy: number, wz: number) -> number,number,boolean` | safe | Projects a world point to screen; returns (sx, sy, visible). Also accounted as a WorldToScreen draw call for overlay stats. |
| `get_screen_center` | `draw.get_screen_center() -> integer,integer` | safe | Returns the current viewport center as two integers (cx, cy) — half of viewport width and height. |
| `get_screen_size` | `draw.get_screen_size() -> integer,integer` | safe | Returns the current viewport width and height as two integers. |
| `get_stats` | `draw.get_stats() -> table` | safe | Snapshot of per-call-type draw counts for this frame — `text`, `line`, `rect`, `circle`, `triangle`, `polygon`, `line_3d`, `circle_3d`, `box_3d`, `arrow_3d`, `sphere_3d`, `world_to_screen`. |

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
| `map_group` | `global_vars.map_group() -> string` | safe | Returns the engine's current map group name, or `"unknown"` when `GlobalVarsBase` is unavailable. |

### game_rules

`table` · tier `safe` — Game-rules clock (PAUSE-ADJUSTED time; differs from global_vars raw clock).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `game_time` | `game_rules.game_time() -> number` | safe | m_flCurrentTime (PAUSE-ADJUSTED clock; differs from global_vars.curtime). |
| `tick_interval` | `game_rules.tick_interval() -> number` | safe | m_flIntervalPerTick (1/64 fallback). |
| `in_match` | `game_rules.in_match() -> boolean` | safe | Alias of `game.IsInGame` — true while the engine reports a live match. |
| `is_connected` | `game_rules.is_connected() -> boolean` | safe | Alias of `game.IsInGame`. Returns true when the engine reports an in-game session. |
| `match_id` | `game_rules.match_id() -> integer` | safe | Returns the current match's `m_unMatchID`; 0 when the game-rules pointer is unavailable. |
| `match_time` | `game_rules.match_time() -> number` | safe | Returns the current match time in seconds from the engine timer system. |
| `real_time` | `game_rules.real_time() -> number` | safe | Returns CGlobalVarsBase::m_flRealTime, or GetGameTime() when globals are unavailable. |
| `tick_count` | `game_rules.tick_count() -> integer` | safe | Returns CGlobalVarsBase::m_nTickCount, or 0 when the globals pointer is unavailable. |
| `tick_to_time` | `game_rules.tick_to_time(tick: integer) -> number\|nil` | safe | Converts a server tick to seconds using the current tick interval; returns nil when the interval isn't available. |
| `time_to_tick` | `game_rules.time_to_tick(seconds: number) -> integer\|nil` | safe | Rounds `seconds` to the nearest tick count using the current tick interval; nil if the interval is not positive. |
| `frame_time` | `game_rules.frame_time() -> number` | safe | Returns the engine `GlobalVarsBase::m_flFrameTime` for the current frame, falling back to `av::combo::get_tick_interval()` when the globals pointer is not available. |
| `get` | `game_rules.get() -> any\|nil` | safe | Returns a `LuaGameRules` wrapper bound to the current `C_CitadelGameRules`; nil when the rules pointer or schema chain is missing. |

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

_No members._

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
| `AlreadyLed` | `.AlreadyLed: boolean` | safe | Set true when the caller has already applied lead to the soul target so the solver skips a second pass. |

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
| `peek_string` | `:peek_string() -> string` | safe | Stub that always returns an empty string; the raw-pointer peek surface is inert. |
| `peek_vec` | `:peek_vec() -> Vector3` | safe | Stub that always returns a zero Vector3; raw pointer peek-vec is not wired. |
| `plus` | `:plus(delta: integer) -> lua_raw_ptr_t` | safe | Returns a new raw pointer offset forward by `delta` bytes. |
| `address` | `:address() -> integer` | safe | Returns the stored raw address as an unsigned integer. |
| `valid` | `:valid() -> boolean` | safe | True when the stored address is non-zero. |
| `get_address` | `:get_address() -> integer` | safe | Returns the raw numeric address held by the pointer. |
| `is_valid` | `:is_valid() -> boolean` | safe | Returns true when the wrapped address is non-zero. |
| `minus` | `:minus(delta: integer) -> lua_raw_ptr_t` | safe | Returns a new raw pointer offset backward by `delta` bytes. |
| `offset` | `:offset(delta: integer) -> lua_raw_ptr_t` | safe | Returns a new raw pointer whose address is `self.addr + delta` (bytes); does not read memory. |
| `peek_bool` | `:peek_bool() -> boolean` | safe | Stub that always returns false; raw-pointer peek paths are not implemented on this surface. |
| `peek_byte` | `:peek_byte() -> integer` | safe | Stub that always returns 0; the raw-ptr peek surface is not wired for byte reads. |
| `peek_float` | `:peek_float() -> number` | safe | Stub that always returns 0; raw-pointer peeks are disabled on this usertype. |
| `peek_int` | `:peek_int() -> integer` | safe | Stub that always returns 0. |
| `peek_ptr` | `:peek_ptr() -> lua_raw_ptr_t` | safe | Stub that always returns an empty raw-pointer handle. |
| `peek_qang` | `:peek_qang() -> Angle` | safe | Stub reader that always returns a zero QAngle; raw peek is not implemented on this type. |
| `peek_qword` | `:peek_qword() -> integer` | safe | Stub reader that always returns 0; raw peeks on this pointer type are not implemented. |
| `peek_short` | `:peek_short() -> integer` | safe | Stub that always returns 0 (raw pointer peek is not wired). |

### hx_hud

`table` · tier `safe` — Bundled HUD helpers shared by the first-party panels: top-bar portrait positions, hero icons, easing, fades, cached menu styles and rounded pills. Load it with local Hud = require("hx_hud").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `portrait_centers` | `hx_hud.portrait_centers(now: number, force?: boolean) -> {[integer]:number}` | safe | Screen x of the centre of every top-bar player portrait, keyed by player slot. The panel walk is cached for 10 s; the first call, force, or a game time that went back refreshes it. The table is shared and refilled in place: read it, do not keep or change it. |
| `portrait_x` | `hx_hud.portrait_x(slot: integer, audience?: string) -> number\|nil` | safe | Screen x of the centre of one top-bar hero portrait. audience "enemy" searches the enemy team, anything else the friendly team. Walks the panels on every call; nil when the HUD or the player is missing or the portrait has no bounds yet. |
| `hero_icon` | `hx_hud.hero_icon(hero_id: integer) -> integer\|nil` | safe | Image handle of a hero's icon (Render.GetHeroIcon), cached once it loads. nil for a nil id or while the icon is not loaded yet; the next call tries again. |
| `in_out_cubic` | `hx_hud.in_out_cubic(t: number) -> number` | safe | Cubic ease-in-out of t in 0..1. |
| `fade_toward` | `hx_hud.fade_toward(v: number, on: boolean, dt: number, rate: number) -> number` | safe | Steps a 0..1 fade value toward 1 when on, else toward 0, by (0.05 / 0.007) * rate * dt, clamped to 0..1. |
| `styles` | `hx_hud.styles(now: number, names?: string[]) -> table` | safe | Cached menu style. With no names, the whole Menu.Style() table; with a list, a table of name -> Menu.Style(name). Refreshed once it is older than 0.5 s. There is one cache per names table, so pass the same constant list on every call. |
| `pill` | `hx_hud.pill(x1: number, y1: number, x2: number, y2: number, color: Color, round: number)` | safe | Filled rectangle with every corner rounded: Render.FilledRectRounded with Render.CORNER_ALL. |

### hx_util

`table` · tier `safe` — Shared helpers for hero scripts: slot math, bit flags, handles, world-target wrapping, timers, rate gates, logging, perf probes. Load it with local U = require("hx_util").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `DEV_BUILD` | `.DEV_BUILD: boolean` | safe | True when capabilities.dll_build() == "dev" (captured at load). Gates log, perf, timed, dev_held_note, and rate_note output. |
| `IN_ALT_CAST` | `.IN_ALT_CAST: integer` | safe | InputBitMask_t.IN_ALT_CAST coerced to integer at load; the alt-cast input bit. |
| `ITEM_SLOT_MAX` | `.ITEM_SLOT_MAX: integer` | safe | Highest 0-based item slot index (7). |
| `ITEM_SLOT_MIN` | `.ITEM_SLOT_MIN: integer` | safe | Lowest 0-based item slot index (4). |
| `MOVE_LOCK_ABILITIES` | `.MOVE_LOCK_ABILITIES: table` | safe | Array of ability-name strings whose cast locks the hero in place: citadel_ability_bebop_laser_beam, ability_charged_shot, citadel_ability_tengu_airlift, ability_icepath, synth_barrage, ability_familiar_ability01. |
| `SLOT_MAX` | `.SLOT_MAX: integer` | safe | Highest 0-based ability slot index (3). |
| `SLOT_MIN` | `.SLOT_MIN: integer` | safe | Lowest 0-based ability slot index (0). |
| `bit` | `hx_util.bit(v: any) -> integer` | safe | math.tointeger(v) or 0: coerces v to a Lua integer, 0 when v is nil or not integer-valued. |
| `by_handle` | `hx_util.by_handle(h: any) -> Entity\|nil` | safe | Normalises h with handle_value and looks it up via entity_list.by_handle; nil for a non-integer h, the 0xFFFFFFFF invalid-handle sentinel, or when no entity matches. |
| `cfg_ability` | `hx_util.cfg_ability(cfg: table, slot0: integer) -> table\|nil` | safe | Returns cfg.abilities[slot0+1] (the per-slot ability config entry) or nil when cfg is falsy, slot0 is not an integer in [0,3], or cfg.abilities is missing. |
| `clamp` | `hx_util.clamp(v: number, lo: number, hi: number) -> number` | safe | Clamps v into [lo, hi]. |
| `clear` | `hx_util.clear(t: table)` | safe | Nils indices #t down to 1 to empty the array part of t; hash keys are left intact. |
| `dev_held_note` | `hx_util.dev_held_note(fmt: string) -> function` | safe | Dev builds: returns held_note(fmt) (a sticky (key, why) logger). Non-dev builds: returns a shared no-op so callers can keep the same shape. |
| `freeze` | `hx_util.freeze(t: any) -> any` | safe | Deep-freezes a table: returns a sealed proxy that reads through to a recursively frozen inner copy and errors on any assignment. Non-table values pass through unchanged. pairs and # still work on the proxy; getmetatable is hidden (__metatable = false). |
| `handle_of` | `hx_util.handle_of(e: Entity) -> integer\|nil` | safe | e:get_handle() reduced through handle_value to a 32-bit integer; nil when e is nil or the raw handle equals the 0xFFFFFFFF sentinel. |
| `handle_value` | `hx_util.handle_value(h: any) -> integer\|nil` | safe | Masks h to its low 32 bits; nil when h is not integer-coercible or already equals the 0xFFFFFFFF invalid-handle sentinel. |
| `held_note` | `hx_util.held_note(fmt: string, gap_s?: number) -> function` | safe | Returns a (key, why) closure that calls log(fmt, key, why) only when why for that key changes from the previously stored value; a nil why clears the stored value without logging. When gap_s is given, one shared rate_gate also caps emissions to at most one per gap_s seconds across all keys. |
| `hl_slot` | `hx_util.hl_slot(slot0: integer) -> integer\|nil` | safe | Converts a 0-based ability slot to its 1-based Lua index (slot0+1); nil when slot0 is not an integer in [0,3]. |
| `imgui_key_to_vk` | `hx_util.imgui_key_to_vk(k: integer) -> integer` | safe | Wraps HeroCfg.key_vk(k): translates an ImGuiKey to a Windows virtual-key code. |
| `interval` | `hx_util.interval() -> number` | safe | global_vars.interval_per_tick() when it reports a sane value in (0.0001, 0.1); otherwise falls back to 1/64. |
| `is_vec` | `hx_util.is_vec(v: any) -> boolean` | safe | True when v is userdata exposing numeric x, y, z fields and a Length function (i.e. a Vector3). Uses pcall internally and is safe on any userdata. |
| `is_world` | `hx_util.is_world(t: any) -> boolean` | safe | True iff t is a table produced by world_target (carries the private marker set when it was wrapped). |
| `item_bit` | `hx_util.item_bit(ability: Ability) -> integer` | safe | InputBitMask_t.IN_ITEM1..IN_ITEM4 for an item ability whose get_slot() returns 4..7; 0 for a nil ability, a non-numeric slot, or any slot outside 4..7. |
| `key_down` | `hx_util.key_down(imgui_key: integer) -> boolean` | safe | Wraps HeroCfg.key_down(imgui_key): true while that ImGuiKey is held. |
| `key_rising` | `hx_util.key_rising(state: table, imgui_key: integer) -> boolean, boolean` | safe | Edge-detect helper: returns (rising, down). down is key_down(imgui_key); rising is true only on the frame it transitions from up to down. The current down state is written to state.prev for the next call; callers pass any plain table they own. |
| `latency` | `hx_util.latency() -> number` | safe | net_channel.get_latency() clamped: returns the raw value when it is in [0, 1), otherwise 0.0. |
| `lead_s` | `hx_util.lead_s() -> number` | safe | Prediction lead in seconds: 2 * interval() + latency(). |
| `local_player_changed` | `hx_util.local_player_changed(ctx: table) -> boolean` | safe | Compares ctx.lp:get_index() with the cached ctx.hero.lp_idx, writes the new index back, and returns true when it differs (local player switched since the last call). |
| `log` | `hx_util.log(fmt: string, ...: any)` | safe | string.format(fmt, ...) prefixed with "[hx] ". Prints to the console in a dev build; when HERO_LIB.dev_mode() is on it additionally forwards the line to HERO_LIB.dev_notify. Silent in a non-dev build with dev_mode off. Falls back to tostring(fmt) if string.format errors. |
| `m_to_u` | `hx_util.m_to_u(m: number) -> number` | safe | HERO_LIB.meters_to_units(m). |
| `modifier_value` | `hx_util.modifier_value(pawn: PlayerPawn, name: string, neutral: any) -> any` | safe | Looks up EModifierValue[name] and returns pawn:get_modifier_value(id, neutral); returns neutral unchanged when the modifier name is not in EModifierValue. |
| `new_gap_detector` | `hx_util.new_gap_detector() -> table` | safe | Returns a fresh { last = -1.0 } state table for tick_gap. |
| `new_rate_gate` | `hx_util.new_rate_gate() -> table` | safe | Returns a fresh { last = -1e9 } state table for rate_ready/rate_fire/rate_reset. |
| `now` | `hx_util.now() -> number` | safe | global_vars.curtime(): server-time seconds. |
| `origin_of` | `hx_util.origin_of(t: any) -> Vector3\|nil` | safe | Vec3 origin: t.origin for a world_target table, HERO_LIB.get_origin(t) for anything else; nil when t is nil. |
| `pawn_of` | `hx_util.pawn_of(t: any) -> any\|nil` | safe | Returns t itself when t is non-nil and not a world_target table; nil otherwise. Lets callers strip world targets out of a target variable to leave only the entity branch. |
| `perf` | `hx_util.perf(name: string) -> table\|nil` | safe | Dev builds: returns a probe object with :add(seconds, now?) that accumulates samples and, every 30 s, prints an [lua-perf] <name> n=.. avg=..us max=..us line and resets. Returns nil in a non-dev build. |
| `rand01` | `hx_util.rand01() -> number` | safe | math.random(): uniform in [0, 1). |
| `rate_fire` | `hx_util.rate_fire(g: table)` | safe | Marks a rate gate as just fired (g.last = now()). |
| `rate_note` | `hx_util.rate_note(gap_s: number) -> function` | safe | Dev builds: returns a (key, fmt, ...) closure that calls log(fmt, ...) at most once per gap_s per key. Keys are held in a weak-keyed table so unreferenced ones do not pin their gate. Non-dev builds: returns a shared no-op. |
| `rate_ready` | `hx_util.rate_ready(g: table, gap?: number) -> boolean` | safe | True when now() - g.last >= (gap or 0.0); use with new_rate_gate and rate_fire. |
| `rate_reset` | `hx_util.rate_reset(g: table)` | safe | Resets a rate gate (g.last = -1e9) so the next rate_ready is immediately true. |
| `roll_chance` | `hx_util.roll_chance(pct: number) -> boolean` | safe | True with probability pct/100; pct is clamped into [0, 100] and treated as 0 when nil. |
| `roll_delay_ms` | `hx_util.roll_delay_ms(kind: integer, lo: number, hi: number) -> number` | safe | kind == 2: uniform random in [lo, hi]. Any other kind: returns lo. lo is floored at 0 and hi is floored at lo, so nil or swapped inputs collapse to lo. |
| `slot_bit` | `hx_util.slot_bit(slot0: integer) -> integer` | safe | HERO_LIB.slot_ability_bit(slot0) as an integer (the input bit for ability slots 0..3); 0 when slot0 is not an integer in [0,3]. |
| `tick` | `hx_util.tick() -> integer` | safe | global_vars.tickcount(). |
| `tick_gap` | `hx_util.tick_gap(d: table) -> boolean` | safe | Updates d.last to now() and returns true when more than 0.30 s elapsed since the previous call; false on the first call (d.last starts at -1.0). Use with new_gap_detector. |
| `tick_restarted` | `hx_util.tick_restarted(d: table) -> boolean` | safe | Writes d.tick = tick() and returns true when the previous d.tick was non-nil and the current tick is lower (demo rewind, match restart, etc.); false on the first call. Takes any plain table the caller owns. |
| `timed` | `hx_util.timed(name: string, fn: function) -> function` | safe | Dev builds: returns a wrapper that times each call to fn with a perf(name) probe and forwards up to two return values. Non-dev builds: returns fn unchanged. |
| `u_to_m` | `hx_util.u_to_m(u: number) -> number` | safe | HERO_LIB.units_to_meters(u). |
| `valid_slot` | `hx_util.valid_slot(slot0: any) -> boolean` | safe | True iff slot0 is a number in [0, 3] with no fractional part. |
| `world_target` | `hx_util.world_target(row: table) -> table\|nil` | safe | Wraps a world-target row { pos\|origin, class, dist, handle, team, enemy, mine } into an opaque table that is_world recognises; the wrapped table exposes pos, origin (falls back to pos), class, dist, handle, team, enemy, mine. Nil when row is not a table or its pos/origin is not a Vector3. |

### hx_steps

`table` · tier `safe` — Step dispatcher used by combo/manual/standalone scripts: compiles cfg.steps into executable steps, resolves aim and targets, drives hx_bus and input leases, and tracks per-step state across ticks. Load it with local Steps = require("hx_steps").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `CAST_PENDING` | `.CAST_PENDING: string` | safe | Cast-outcome tag "pending": cast_mark/cast_outcome is still waiting to decide. |
| `CAST_REFUSED` | `.CAST_REFUSED: string` | safe | Cast-outcome tag "refused": the mark's deadline passed with no cast detected. |
| `CAST_TAKEN` | `.CAST_TAKEN: string` | safe | Cast-outcome tag "started": the ability's cooldown/charges/channeling confirms a cast happened. |
| `COMBO_WAIT_WINDOW` | `.COMBO_WAIT_WINDOW: number` | safe | Max seconds a combo-sourced step will wait on cooldown before giving up (1.0). Also used as the extra grace tacked onto the per-step cd_until deadline. |
| `CONVERGE_GRACE_S` | `.CONVERGE_GRACE_S: number` | safe | Seconds hybrid-aim delivery and face-action steps wait for the crosshair to converge before committing or giving up (0.45). |
| `DEFAULT_AIM` | `.DEFAULT_AIM: table` | safe | Fallback aim table used when a step has no slot aim: psilent mode, require_target+visibility, 60 FOV, enemy target_mode, prediction on, torso hitboxes, no range cap. |
| `ECHO_GRACE_S` | `.ECHO_GRACE_S: number` | safe | Seconds an echo-sourced ability step keeps waiting on cooldown after arrival before falling through to skip (0.45). |
| `FIRED` | `.FIRED: string` | safe | Verdict "fired": the step pressed and consumed its slot; the runner should advance. |
| `FIRED_FREE` | `.FIRED_FREE: string` | safe | Verdict "fired_free": the step pressed but does not block subsequent steps this tick (delay/innate/face/cancel/dash/alt_fire). |
| `GATE` | `.GATE: table` | safe | Gate modes passed as opts.gate to resolve: GATE.FULL (full Tgt.can_cast check), GATE.REACH (reach-only), GATE.NONE (skip targeting checks entirely). |
| `HOLD` | `.HOLD: string` | safe | Verdict "hold": the step is still mid-cast; the runner should re-enter it next tick via engaged_reentry. |
| `PLACE_GRACE_S` | `.PLACE_GRACE_S: number` | safe | Seconds a unit-targeted ability waits for ability:can_place_on(target) to pass before skipping with no-valid-target (0.25). |
| `SKIP` | `.SKIP: string` | safe | Verdict "skip": the runner should move on without pressing; step.skip_reason is set. |
| `UNCAPPED_RANGE_M` | `.UNCAPPED_RANGE_M: number` | safe | Sentinel "effectively uncapped" range in metres (100000.0) for aim tables that should not clamp range. |
| `WAIT` | `.WAIT: string` | safe | Verdict "wait": the step is blocked for a known reason this tick (step.wait_reason/wait_detail are set). |
| `WAIT_THRESHOLD` | `.WAIT_THRESHOLD: number` | safe | Max cooldown seconds a non-combo step will wait on before skipping (0.5). |
| `abandon` | `hx_steps.abandon(ctx: table, why?: string)` | safe | Drops the currently engaged (HOLD) step: clears its engagement flag, invokes its stored on_abandon callback, fires the on_step_abandoned hook, and releases its input at Inp.PRIO.OVERRIDE. No-op when nothing is engaged or ctx is nil. |
| `aim_disabled` | `hx_steps.aim_disabled(step: table) -> boolean` | safe | True when step.aim is missing or step.aim.mode equals Cfg.AIM.DISABLED. |
| `aim_off` | `hx_steps.aim_off(ctx: table, step: table) -> boolean` | safe | True when aim_disabled(step) is true or ctx.no_script_aim[step.eff_slot] is true — i.e. script aim is turned off for that effective slot. |
| `auto_slot_ready` | `hx_steps.auto_slot_ready(ctx: table, step: table) -> boolean` | safe | Readiness probe for auto-cast steps. Returns true immediately when step.state.engaged. Otherwise requires: ability in slot with can_activate; if fires_when=TARGET_VISIBLE a visible target; slot_cond_ok (enemy_in_range/not_in_air/would_kill); slot_opts.delay_ms + ability's AbilityCastDelay windup to have elapsed since conditions first held; and action.decide("offense_auto", slot_act) returning "act". Clears step.state.cond_t0 when conditions fail. |
| `cast_mark` | `hx_steps.cast_mark(ab: Ability, tick: integer) -> table` | safe | Snapshots ab:get_cooldown_start / true_cooldown / get_remaining_charges at tick and computes latency-aware tick deadlines (answer, deadline, cap). The returned mark is fed to cast_outcome later to classify whether the press became a real cast. |
| `cast_outcome` | `hx_steps.cast_outcome(mark: table, tick: integer) -> string,number\|nil` | safe | Classifies a cast_mark at the current tick. Returns CAST_TAKEN (with the detected game time) when cooldown_start jumped, true_cooldown rose by >0.05, remaining_charges dropped, is_channeling, or the ability stopped being activatable. Stays CAST_PENDING while tick < mark.answer, or while in_cast_delay/HERO_LIB.is_busy and tick < mark.cap. CAST_REFUSED once tick passes mark.deadline with none of the above. |
| `clear_state` | `hx_steps.clear_state(step: table)` | safe | Empties step.state in place without reallocating. No-op when state is already empty. |
| `combo_running` | `hx_steps.combo_running(ctx: table) -> boolean` | safe | True when ctx.combo exists and ctx.combo.mode == "combo" — i.e. the active driver is the combo runner, not manual or standalone. |
| `combo_slots` | `hx_steps.combo_slots(ctx: table) -> table` | safe | Memoised set of ability slots referenced by cfg.steps rows (c[slot] = true) plus c.alt = true when any ACTION row uses ALT_FIRE, and c.ver = cfg.version. Cached on ctx.hero.combo_slots_memo and rebuilt in place when cfg.version changes. |
| `compile_combo` | `hx_steps.compile_combo(cfg: table) -> table` | safe | Compiles cfg.steps into an ordered list of executable step tables (ability/item/delay/face/cancel/dash/alt_fire/innate). Inserts a fixed cfg.combo_delay_ms gap between adjacent non-wait rows, respects per-row delay_kind/min/max, and leaves out rows with unknown kinds. Returns {} when has_steps(cfg) is false. |
| `compile_manual` | `hx_steps.compile_manual(cfg: table, slot0: integer) -> table` | safe | Compiles a manual press of slot0. If cfg has explicit steps, returns just the ability step for slot0. Otherwise wraps the ability with the slot's manual_items at TIMING.BEFORE and TIMING.AFTER (sorted by priority/sequence) and defers self-silencing items to the tail. Returns {} when the ability is unknown. |
| `compile_standalone` | `hx_steps.compile_standalone(cfg: table) -> table` | safe | Compiles the standalone/auto-item step list. When cfg has no explicit steps and items are enabled it inserts standalone.combo_items at BEFORE+AFTER timings; it then appends cfg.item_pool entries that are not already covered by prior steps. Returns {} when cfg.items_enabled is false. |
| `complete` | `hx_steps.complete(ctx: table, step: table, verdict?: string) -> string` | safe | Finishes a cast: banks the ability's AbilityChannelTime onto step.state.credit, fires the on_after_cast hook, and returns verdict (defaulting to FIRED). |
| `declare_wait` | `hx_steps.declare_wait(step: table, secs: number)` | safe | Adds secs to step.state.credit when secs is a positive number. Non-numbers and non-positive values are ignored. |
| `declared_wait` | `hx_steps.declared_wait(step: table) -> number` | safe | Drains and returns the banked wait credit on step.state.credit, resetting it to 0. |
| `deliver` | `hx_steps.deliver(ctx: table, step: table, opts?: table) -> string` | safe | Issues the aim/fire request through hx_bus. When step.aim_pos is nil but aim.require_target is false it presses (or calls opts.on_fire) and completes with opts.verdict (defaulting to FIRED). For HYBRID aim it steers until Bus.aim_on_target or CONVERGE_GRACE_S elapses, returning HOLD meanwhile. Otherwise it submits a Bus.request with psilent per aim.mode (or opts.psilent) and returns FIRED on Bus.FIRED, HOLD on Bus.PENDING, else WAIT with step.wait_reason="bus". |
| `ends_tick` | `hx_steps.ends_tick(verdict: string) -> boolean` | safe | True when the verdict ends the runner's current tick: WAIT, HOLD, or FIRED. |
| `exec` | `hx_steps.exec(ctx: table, step: table) -> string` | safe | Dispatches step to the executor for its kind (ability/item/delay/melee/innate/face/cancel/dash/alt_fire). Preempts any other engaged step via abandon("preempted") first and clears step.wait_reason/wait_detail/skip_reason before dispatch. Returns SKIP for unknown kinds. |
| `has_steps` | `hx_steps.has_steps(cfg: any) -> boolean` | safe | True when cfg is a table whose .steps is a non-empty table. |
| `is_acting` | `hx_steps.is_acting(verdict: string) -> boolean` | safe | True when verdict is FIRED or FIRED_FREE. |
| `persistent` | `hx_steps.persistent(ctx: table, key: string, slot: integer, source: string) -> table` | safe | Returns ctx.hero[key] if it exists, otherwise creates a fresh ability step {kind="ability", slot, host_slot=slot, source, state={}} and stores it under key. The returned step persists across ticks, so step.state survives. |
| `press` | `hx_steps.press(ctx: table, step: table, prio?: integer, as_made?: boolean) -> table` | safe | Acquires a lease at prio (default Inp.PRIO.STEP) and presses what the step needs: l:item() for item kind; otherwise l:press_spec(spec) when a press spec exists for the slot; l:item() when the ability casts by mode and as_made is false; else splits IN_ATTACK2 out to l:alt_fire and sends the rest through l:press(bits). Also issues l:alt_cast() when aim.target_mode is SELF. Returns the lease. |
| `release` | `hx_steps.release(ctx: table, step: table, prio?: integer) -> table` | safe | Acquires a lease at prio (default Inp.PRIO.CHARGE) and clears the step's input bits: U.item_bit(ability) for items; the spec's bs1\|bs2\|bs3 bits when a press spec exists; otherwise step.bits. Returns the lease. |
| `reset` | `hx_steps.reset(step: table)` | safe | Clears the resolved per-tick fields on step (target, aim_pos, ability, eff_slot, bits, aim, direct_press). Leaves step.state untouched. |
| `resolve` | `hx_steps.resolve(ctx: table, step: table, opts?: table) -> boolean,string\|nil` | safe | Picks the target and aim point for a step and runs the gate at opts.gate (default GATE.FULL). Honours opts.target+no_pick, opts.target_mode, opts.aim_pos, opts.ground (aim at origin_of(target)). Writes step.target and step.aim_pos, fires on_before_cast, then returns (true) on pass or (false, verdict, why) with SKIP for hard refusals and WAIT for recoverable "reach"/"blocked" cases. |
| `row_script_aim` | `hx_steps.row_script_aim(ctx: table, kind: integer, slot: integer) -> boolean` | safe | Reads ctx.cfg.slot_opts[kind][slot+1].script_aim: returns false only when that nested option explicitly disables script aim, true otherwise (including when the option table is missing). |
| `slot_act` | `hx_steps.slot_act(slot: integer) -> string\|nil` | safe | Maps a 0-based slot to its action name: 0..3 -> "ability1".."ability4", 4..7 -> "item1".."item4". Returns nil for other inputs. |
| `slot_cond_ok` | `hx_steps.slot_cond_ok(ctx: table, o: table, ability: Ability, target: any, aim: table) -> boolean` | safe | Evaluates the row-option conditions in o.cond. enemy_in_range: requires a pawn and ability; uses aim.max_range_m (converted to units) or HERO_LIB.get_cast_range(ability); when that cap is in (0, 3999) rejects targets beyond it. not_in_air: fails when the local player is not on the ground. would_kill: requires HERO_LIB.is_lethal(ability, pawn). Missing cond or missing o returns true. |
| `wait_bounded` | `hx_steps.wait_bounded(step: table) -> boolean` | safe | True when step.wait_reason is one of delay/cooldown/busy/cc/gated/no-valid-target — i.e. the wait is expected to resolve on its own and the runner can keep holding. |

### hx_opts

`table` · tier `safe` — Declares a hero's ComboOpt options and features once per hero_id and reads their current values. Load it with local Opts = require("hx_opts").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ensure` | `hx_opts.ensure(H: table)` | safe | Declares H.options and H.features into ComboOpt the first time it is called for H.hero_id. Each option becomes a hero-scoped widget on the item or ability scope (toggle/slider/slider_int/enum/color/header/hint/multi); keys and depends_on are namespaced per hero. Subsequent calls for the same hero_id are no-ops; invalid slots fall back to slot 0 with a log line, and unknown kinds are logged and skipped. |
| `get` | `hx_opts.get(H: table, key: string, fallback?: any) -> any` | safe | Reads the current ComboOpt value for the per-hero scoped key. Returns fallback when H is nil or when ComboOpt.get returned nil. |
| `reset` | `hx_opts.reset(hero_id?: integer)` | safe | Clears the "already declared" record so ensure will re-declare on next call: a single hero when hero_id is given, otherwise every hero. |

### hx_cfg

`table` · tier `safe` — Hero-config helpers: fetches the active cfg, exposes HeroCfg enum tables, resolves per-slot ability/aim/helper settings, and drives the combo-key gate and manual-fire session calls. Load it with local Cfg = require("hx_cfg").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ACTION` | `.ACTION: table` | safe | HeroCfg.enums().ACTION — named step-action codes. |
| `AIM` | `.AIM: table` | safe | HeroCfg.enums().AIM — named aim-mode codes (NORMAL, PSILENT, HYBRID, ...). Compare slot aim modes against these. |
| `CHARGE` | `.CHARGE: table` | safe | Charge-release-mode codes used by release_at: { FULL = 0, CAP = 1, LETHAL = 2 }. |
| `COND` | `.COND: table` | safe | HeroCfg.enums().COND — named condition codes for conditional steps. |
| `DELAY` | `.DELAY: table` | safe | Step-delay kinds: { NONE = 0, FIXED = 1, RANDOM = 2 }. |
| `FIRES` | `.FIRES: table` | safe | HeroCfg.enums().FIRES — helper fires-when codes (YOU_CAST, TARGET_VISIBLE, COOLDOWN_READY, ...). |
| `MODE_ALWAYS` | `.MODE_ALWAYS: integer` | safe | HeroCfg.enums().MODE.ALWAYS — combo-key mode that treats the gate as always on. |
| `MODE_HOLD` | `.MODE_HOLD: integer` | safe | HeroCfg.enums().MODE.HOLD — combo-key mode that latches only while the key is held. |
| `MODE_TOGGLE` | `.MODE_TOGGLE: integer` | safe | HeroCfg.enums().MODE.TOGGLE — combo-key mode that toggles the latch on each press. |
| `REPEAT` | `.REPEAT: table` | safe | HeroCfg.enums().REPEAT — named step-repeat codes. |
| `SCOPE` | `.SCOPE: table` | safe | Step-scope codes: { SELF = 0, ENEMY = 1, STEP_TARGET = 2 }. |
| `STEP` | `.STEP: table` | safe | HeroCfg.enums().STEP — named step-kind codes. |
| `TARGET` | `.TARGET: table` | safe | HeroCfg.enums().TARGET — named target-selection codes. |
| `TIMING` | `.TIMING: table` | safe | HeroCfg.enums().TIMING — named timing-mode codes. |
| `ability` | `hx_cfg.ability(cfg: table, slot0: integer) -> table\|nil` | safe | Returns cfg.abilities[slot0+1] (the per-slot ability config subtable), or nil when cfg is missing or slot0 is not an integer in 0..3. |
| `ability_order` | `hx_cfg.ability_order(cfg: table) -> table` | safe | Returns an integer array of all four ability slots (0..3) in the order given by cfg.ability_order, de-duplicated, with any missing slots appended afterwards. Invalid entries in cfg.ability_order are skipped. |
| `aim` | `hx_cfg.aim(cfg: table, slot0: integer) -> table\|nil` | safe | Convenience for ability(cfg, slot0).aim — the per-slot aim config subtable, or nil when the slot has none. |
| `autonomous` | `hx_cfg.autonomous(cfg: table, slot0: integer) -> boolean, integer` | safe | Alias for helper_autonomous. |
| `clear_gate` | `hx_cfg.clear_gate()` | safe | Forces the combo-key latch off. The next combo_gate call still re-reads the key state. |
| `combo_gate` | `hx_cfg.combo_gate(cfg: table, combo_running: boolean) -> boolean` | safe | Edge-triggered combo-key gate: debounces HERO_LIB.combo_key for the vk mapped from cfg.combo_key, under cfg.combo_key_mode (HOLD/TOGGLE/ALWAYS). Latches on rising edge (if combo_running is false) and clears on release in HOLD mode. Returns true while the latch is on. Key 0 always returns false; MODE_ALWAYS always returns true; cfg changes rebind the key with a 4-tick zero-key debounce and a 6-tick release debounce. Caches a single module-level gate state — not safe for use from more than one caller. |
| `combo_held` | `hx_cfg.combo_held() -> boolean` | safe | Debounced down-state of the combo key from the last combo_gate call. Does not sample the key itself. |
| `combo_on` | `hx_cfg.combo_on(ctx: table) -> boolean` | safe | True when combos should run: false if ctx.cfg.combo_enabled is explicitly false; true if ctx.combo.mode == "combo" or combo_key_mode is MODE_ALWAYS; otherwise requires cfg.combo_key > 0 and combo_held(). |
| `discard` | `hx_cfg.discard(slot0: integer) -> any` | safe | Pass-through to HeroCfg.discard(slot0) — discards the pending manual-fire session for that slot. |
| `get` | `hx_cfg.get() -> table` | safe | Returns the active HeroCfg config table (HeroCfg.get()). |
| `helper_autonomous` | `hx_cfg.helper_autonomous(cfg: table, slot0: integer) -> boolean, integer` | safe | Returns (autonomous, fires_when): autonomous is true when helper_fires_when is TARGET_VISIBLE or COOLDOWN_READY. slot0 == nil returns (false, FIRES.YOU_CAST). |
| `helper_fires_when` | `hx_cfg.helper_fires_when(cfg: table, slot0: integer) -> integer` | safe | Returns the helper fires-when code for cfg.slot_opts.helper[slot0+1].fires_when, upgrading YOU_CAST to COOLDOWN_READY. Falls back to COOLDOWN_READY when slot_opts.helper[slot0+1] is missing. On dev builds, logs each unique (slot, raw, delay_ms, upgraded) tuple once via U.log. |
| `helper_fires_when_raw` | `hx_cfg.helper_fires_when_raw(cfg: table, slot0: integer) -> integer` | safe | Returns the raw cfg.slot_opts.helper[slot0+1].fires_when with no YOU_CAST upgrade. Defaults to FIRES.YOU_CAST when the entry is missing. |
| `hero_id` | `hx_cfg.hero_id() -> integer` | safe | Returns HeroCfg.hero_id() — the current hero's id. |
| `manual_enabled` | `hx_cfg.manual_enabled(slot0: integer) -> any` | safe | Pass-through to HeroCfg.manual_enabled(slot0) — whether a manual-fire binding is enabled for that slot. |
| `manual_keepalive` | `hx_cfg.manual_keepalive(slot0: integer) -> any` | safe | Pass-through to HeroCfg.manual_keepalive(slot0) — keeps the manual-fire session for that slot alive this tick. |
| `manual_triggered` | `hx_cfg.manual_triggered(slot0: integer) -> any` | safe | Pass-through to HeroCfg.manual_triggered(slot0) — whether the slot's manual-fire binding fired this tick. |
| `note_autofire` | `hx_cfg.note_autofire(ctx: table, tag: string, label: string, slot0: integer, autonomous: boolean, fw: integer)` | safe | Dev-build-only diagnostic: when the autonomous flag for a slot changes against ctx.hero["autofire_<slot0\|label>"], logs the transition and the fires_when code. No-op on non-dev builds. |
| `relatch` | `hx_cfg.relatch()` | safe | Forces the combo-key latch on without changing the sampled key state. |
| `release` | `hx_cfg.release(slot0: integer) -> any` | safe | Pass-through to HeroCfg.release(slot0) — releases the held manual-fire session for that slot. |
| `replays` | `hx_cfg.replays() -> any` | safe | Pass-through to HeroCfg.manual_replays() — the current manual-replay count/list. |
| `session_open` | `hx_cfg.session_open(slot0: integer) -> any` | safe | Pass-through to HeroCfg.session_open(slot0) — whether a manual-fire session is currently open for that slot. |
| `show_combo_target` | `hx_cfg.show_combo_target(cfg: table) -> boolean` | safe | Returns the cached heroes/content/show_combo_target native setting (false only when the native value is explicitly false). Re-reads the native only when the cfg view changes identity. |
| `swallow` | `hx_cfg.swallow(slot0: integer) -> any` | safe | Pass-through to HeroCfg.swallow(slot0) — consumes the pending user press for that slot so it does not fire the real ability this tick. |
| `user_holding` | `hx_cfg.user_holding(slot0: integer) -> any` | safe | Pass-through to HeroCfg.user_holding(slot0) — whether the user is currently holding the slot's ability button. |
| `user_pressed` | `hx_cfg.user_pressed(slot0: integer) -> any` | safe | Pass-through to HeroCfg.user_pressed(slot0) — whether the user pressed the slot's ability button this tick. |
| `uses_mouse` | `hx_cfg.uses_mouse(mode: integer) -> boolean` | safe | True when mode is AIM.NORMAL or AIM.HYBRID — the aim modes that rely on the real mouse direction. |
| `uses_psilent` | `hx_cfg.uses_psilent(mode: integer) -> boolean` | safe | True when mode is AIM.PSILENT or AIM.HYBRID — the aim modes that use psilent angles. |
| `version` | `hx_cfg.version() -> integer` | safe | Returns HeroCfg.version() — the active config's revision counter, bumped when the config reloads. |

### hx_charge

`table` · tier `safe` — Charged-ability timing helpers: resolves full/min charge time and min-damage percent from scaled or vdata properties (caching on the slot state table), reads the engine charge-start clock, and derives the hold fraction needed to kill or to hit a damage cap. Load it with local Charge = require("hx_charge").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `clock` | `hx_charge.clock(ab: Ability) -> number\|nil` | safe | Returns the first positive value among ab.m_flChargeStartTime, m_flScopeStartTime, m_flStateStartTime — the engine's charge-start timestamp. nil when none of the fields read as a positive number. |
| `fraction` | `hx_charge.fraction(ab: Ability, st: table, now: number) -> number` | safe | Charge fraction in [0, 1 + min_time/full_time]. Returns 0 when st.chg_full is not a positive number or st.chg_t0 is unset. Uses st.chg_t0 as the zero time, but prefers the engine clock() when it is within 50 ms of (st.chg_t0, now). |
| `full_time` | `hx_charge.full_time(ab: Ability, st: table) -> number\|nil` | safe | Full-charge duration in seconds. Reads the first positive scaled property among TimeToFullCharge/ChargeTime/MaxChargeDuration, else the CCitadelAbilityChargedBombVData.m_flChargeForMaxDamage vdata row. Caches on st.chg_full (false when none is found); subsequent calls return the cached value and skip the lookup. Warns once per session (via U.log) when an ability advertised as Charged exposes no charge-time property. |
| `lethal_frac` | `hx_charge.lethal_frac(ab: Ability, pawn: PlayerPawn, st: table, kill_dmg?: number) -> number\|nil` | safe | Charge fraction in [0, 1] required for the shot to kill pawn, after accounting for the ability's MinChargeDamagePercent. Uses kill_dmg if a positive number, else HERO_LIB.lethality(ab, pawn).damage. Returns nil when ab/pawn is missing, min_damage_frac is unknown (warns once), lethality is invalid, damage or hp is non-positive, or the full-damage shot still cannot kill; returns 0 when min damage already kills or minp >= 1.0. |
| `min_damage_frac` | `hx_charge.min_damage_frac(ab: Ability, st: table) -> number\|nil` | safe | Minimum-damage charge fraction (MinChargeDamagePercent / 100, clamped to [0.05, 1.0]), or nil when the property is absent. Caches on st.chg_minp (false when unknown). |
| `min_time` | `hx_charge.min_time(ab: Ability, st: table) -> number` | safe | Minimum charge time in seconds, from the CAbilityHornetSnipeVData.m_flMinScopeTimeToShoot vdata row; 0.0 when absent. Cached on st.chg_min. |
| `release_at` | `hx_charge.release_at(ab: Ability, aim: table, pawn: PlayerPawn, st: table) -> number` | safe | Charge fraction to hold until release, including the min-charge-time overshoot (min_time / full_time). Returns 1.0 when full_time is not a positive number. Mode (aim.charge_mode, default CHARGE.FULL): LETHAL uses lethal_frac(ab, pawn, st, aim.kill_dmg) or 1.0; CAP uses max(aim.charge_cap_pct/100 clamped to [0.01, 1.0], lethal_frac or 0); FULL uses 1.0. On dev-mode builds, logs a diagnostic line at most once every 0.3 s via st.chg_diag_at. |

### hx_input

`table` · tier `safe` — Shared per-tick input dispatcher. Scripts open leases at a priority, stage presses/clears/move/innates, and commit() resolves them against the UserCmd — gated by action.decide(role, act) and arbitrated so higher-prio bits win and equal-prio clears outrank presses. Load it with local Input = require("hx_input").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `PRIO` | `.PRIO: table` | safe | Priority ladder used by acquire(): MOVEMENT=5, STEP=10 (default), AUTO=20, CHARGE=30, SURVIVAL=35, OVERRIDE=40. Higher priority wins a contested bit; equal priority lets clears beat presses. |
| `acquire` | `hx_input.acquire(owner?: string, priority?: integer, role?: string) -> InputAcquire` | safe | Open a lease at the given priority (defaults to PRIO.STEP). role defaults to "move" at or below PRIO.MOVEMENT, "defense" at PRIO.SURVIVAL, else "offense_auto"; passing an unknown role errors. owner is a short label used for logging and move-tie-breaking (defaults to "?"). The returned InputAcquire is registered with the shared dispatcher and resolved on the next commit(). |
| `active` | `hx_input.active() -> boolean` | safe | true while a dispatch tick is open — set by begin_tick, cleared by commit or discard. |
| `allowed` | `hx_input.allowed(owner: string, role: string, act: string, in_progress?: boolean) -> boolean` | safe | Query action.decide(role, act) for this tick, memoised per (role, act). Returns true when the verdict is "act", or when in_progress is true and the verdict is "hold" with an in-progress reason (Cooldown, NoCharges, NotReady, CastDelay, Channel, Busy, Selected, Meleeing, NoStamina, NoAirMoves, Reloading, ClipEmpty, Form, GameRefused). On "cancel" also calls HERO_LIB.innate_release_all once per tick. Errors on an unknown role. Resets per-tick state if the tick advanced since the last call. |
| `begin_tick` | `hx_input.begin_tick(cmd: table)` | safe | Mark the input tick open and record the UserCmd. Fully resets lease and verdict state if the tick changed or the previous tick was aborted; if a new command_number appears on the same tick, resets just the lease state (keeps action.decide verdicts) and logs the drop in dev builds. |
| `buttons` | `hx_input.buttons(cmd: table) -> integer` | safe | cmd.button_state0 as integer; 0 when cmd is nil. |
| `commit` | `hx_input.commit()` | safe | Resolve every open lease onto the stored UserCmd. For each lease, gates its (p1\|p2\|p3) press bits per-bit via action.decide(role, act) and drops disallowed bits; then stakes press/clear across all leases per field, with higher-prio winning and clears beating presses at equal prio; writes the winning bits via cmd:add_buttonstate{1,2,3} and cmd:clear_buttonstate{1,2,3}. Also stages the winning move triplet and HERO_LIB.innate_press each requested innate. No-op if the tick changed, was discarded, or no cmd is stored. Clears all leases and closes the tick. |
| `discard` | `hx_input.discard()` | safe | Abort the open tick. Clears every lease and verdict, drops the stored cmd, and marks the tick aborted so the next begin_tick on the same tick starts fresh. |
| `held` | `hx_input.held(cmd: table, bits: integer) -> boolean` | safe | true when (cmd.button_state0 & bits) is non-zero. False when either side is zero. |
| `innate_act` | `hx_input.innate_act(id: integer) -> string\|nil` | safe | Action name for a HERO_LIB.INNATE.* id: LIGHT_MELEE/HEAVY_MELEE→"melee"/"heavy_melee", PARRY→"parry", SLIDE→"slide", JUMP→"jump", MANTLE→"mantle", ZIPLINE→"move", DASH_JUMP→"dash". nil for unknown ids. |
| `move_of` | `hx_input.move_of(cmd: table) -> number,number,number` | safe | cmd.forwardmove, cmd.leftmove, cmd.upmove, each 0.0 for missing fields; returns three zeros when cmd is nil. |
| `release_all` | `hx_input.release_all()` | safe | HERO_LIB.innate_release_all(); drops any held innate on the UserCmd pipeline. |
| `report` | `hx_input.report(owner: string)` | safe | Print an [av-test] press/held-drop summary for one owner, grouped by why. No-op outside DEV_BUILD. |

### InputAcquire

`table` · tier `safe` — Returned by hx_input.acquire(owner, priority?, role?). Batches press/clear requests for one owner at one priority; the shared hx_input.commit() resolves it against every other live lease. Builder methods all return self so calls chain.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `alt_cast` | `:alt_cast() -> InputAcquire` | safe | Press the alt-cast bit (U.IN_ALT_CAST) into fields 1 and 2. If a prior :item saw the fire bit pressed (confirm_act set), first un-presses the fire bit from field 2 and ORs the staged cast_bit (slot bit for 0..3, else item bit) into fields 1 and 2 so alt-cast fires that slot/item instead of the primary; clears confirm_act after. |
| `alt_fire` | `:alt_fire(act?: string, fields?: table) -> InputAcquire` | safe | OR ALT_FIRE_BIT (IN_ATTACK2) into press fields (defaults to {1,2} when fields is nil). Records this lease's alt bit as action act for commit-time gating; when act is nil defaults to "shoot" and marks the bit unowned so the gate uses the lease's role-default act instead. |
| `clear` | `:clear(bits: integer, fields?: table) -> InputAcquire` | safe | OR bits into the lease's clear masks. fields is a table of 1..3 field indices; nil ORs into c1, c2 and c3. Clears outrank presses of equal priority at commit, so this is a strong force-off. |
| `innate` | `:innate(id: integer) -> InputAcquire` | safe | Request that HERO_LIB innate id be pressed on commit at this lease's priority. Non-number or negative id is ignored. Only the highest-prio requester wins per id; equal priority does not override an existing request. |
| `item` | `:item(ability: Ability) -> InputAcquire` | safe | Call ability:get_cast_buttons() and OR the held bits into p1 and the pressed bits into p2. If pressed contains the fire bit, records confirm_act (ability1..ability4 / item1..item4 for valid slots 0..7) and cast_bit (slot_bit for 0..3, else ability item_bit), which a later :alt_cast then redirects the fire press to. nil ability is a no-op. |
| `move` | `:move(fwd?: number, side?: number, up?: number) -> InputAcquire` | safe | Stage a cmd.forwardmove/leftmove/upmove triplet. Only kept when this lease has strictly higher prio than the current staged move, or equal prio with a lexicographically smaller owner string. On commit, the winning triplet is gated via action.decide(role, "move") and only non-nil components overwrite the UserCmd. |
| `press` | `:press(bits: integer, fields?: table) -> InputAcquire` | safe | OR bits into the lease's press masks. fields is a table of 1..3 field indices; nil ORs into p1 and p2 only (not p3). bits that fail to tointeger or are 0 are a no-op. |
| `press_slot` | `:press_slot(slot0: integer) -> InputAcquire` | safe | :press(U.slot_bit(slot0)). slot0 must be 0..3; outside that range slot_bit returns 0 and nothing is staged. |
| `press_spec` | `:press_spec(spec: table) -> InputAcquire` | safe | OR spec.bs1 / spec.bs2 / spec.bs3 into p1 / p2 / p3 respectively. Missing fields are skipped; nil spec is a no-op. Lets callers pre-build a per-field press pattern (e.g. "press in field 1 only"). |
| `presses` | `:presses(bits: integer) -> boolean` | safe | true when ((p1\|p2\|p3) & bits) is non-zero on THIS lease only — does not consult other leases or the final gated outcome. |

### hx_target

`table` · tier `safe` — Targeting primitives: hitbox-bit encoding, enemy/teammate/class picking, aim-point resolution, can-cast gating and kill-plan lethality. Load it with local T = require("hx_target").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `FORCE_HEAD` | `.FORCE_HEAD: integer` | safe | Hitbox bit mask (enable\|priority for the HEAD slot) that pins hitbox selection to head only. Equals force_hitbox(HITBOX.HEAD). |
| `HITBOX` | `.HITBOX: table` | safe | 1-based slot indices for the hitboxes array consumed by hitbox_bits: HEAD=1, NECK=2, TORSO=3, ARMS=4, LEGS=5. |
| `LINE_FILTER` | `.LINE_FILTER: table` | safe | Trace filter used by line_clear: { mask=1839107, exclude=0, interacts_as=0, objects=7, group=4 }. Reused across calls — treat as read-only. |
| `RANGE_SENTINEL_U` | `.RANGE_SENTINEL_U: number` | safe | 3999.0 source units. Any ability cast_range at or above this is treated as "unlimited" by pick() and the range falls back to aim.max_range_m or the combo target config instead. |
| `UNCAPPED_COMBO_QUERY` | `.UNCAPPED_COMBO_QUERY: table` | safe | Canned find_combo_target query { max_range_m=100000.0, require_visible=false } for scripts that need no range or LOS gate. Shared table — do not mutate. |
| `ability_in_slot` | `hx_target.ability_in_slot(lp: PlayerPawn, slot0: integer) -> Ability\|nil` | safe | lp:get_ability_by_slot(slot0) when slot0 is 0..3; nil otherwise or when lp is nil. |
| `aim_point` | `hx_target.aim_point(ctx: table, aim: table, ability: Ability, target: any) -> Vector3\|nil,string\|nil` | safe | Pick the final world point to aim at for this ability on target. For a world target, returns target.origin when aim.aim_at_ground, else target.pos or target.origin, optionally re-centred around the densest enemy cluster inside the ability's aoe when aim.aim_at_cluster. For a pawn, honours aim.aim_at_ground, aim.aim_at_cluster (clustering teammates when target is a teammate), then (unless aim.use_prediction is false) HERO_LIB.predict_lead_point backtrack and HERO_LIB.predict_projectile_simulated lead, finally falling back to hx_aim.resolve_point for the slot and HERO_LIB.get_target_pos. Returns nil, "blocked" when projectile prediction reports blocked; nil for a nil target. |
| `any_enemy` | `hx_target.any_enemy(origin: Vector3, radius_u: number) -> boolean` | safe | true when at least one non-ignored enemy hero sits within radius_u (source units) of origin. Uses HERO_LIB.get_heroes_in_radius and HERO_LIB.should_ignore_target. |
| `best_enemy` | `hx_target.best_enemy(origin: Vector3, radius_u: number, opts?: table) -> PlayerPawn\|nil` | safe | Pick the closest non-ignored enemy hero in the radius, scoring visible targets ahead of occluded ones. opts.fov_deg clips to that FOV around the local view; opts.strict re-checks the hero's aim-pos distance against radius_u (not just origin). nil when no candidate matches. |
| `can_cast` | `hx_target.can_cast(ctx: table, aim: table, ability: Ability, target: any, pos: Vector3) -> boolean,string\|nil` | safe | Full cast-gate check at (target, pos). Returns true, nil or false plus a short reason: "no-target" (aim.require_target), "no-aimpoint" (target without pos), "out-of-range" (HERO_LIB.ability_in_range or world reaches_pos), "max-range" / "min-range" (aim.max_range_m / aim.min_range_m against ctx.lp cast origin), "hp-band" (aim.min_hp_pct / aim.max_hp_pct), "fov" (aim.max_fov scaled by hx_aim.scale_fov against the slot), "los" (aim.require_visibility != false, HERO_LIB.no_obs_to_pos), "not-lethal" (aim.only_when_lethal + HERO_LIB.is_lethal), "min-enemies" (aim.is_ground_aoe + aim.min_enemies, counted at pos), "self-hp" / "self-min-enemies" (aim.is_self_cast with self_cast_hp_pct and min_enemies around lp), "refire" (aim.min_refire_s + HERO_LIB.recently_cast), "reach" (PSILENT mode without aim.allow_unsafe_psilent, via hx_bus.reach_ok). Self cast target (target == ctx.lp) skips range/FOV/LOS gates. |
| `enemies_in_radius` | `hx_target.enemies_in_radius(ctx: table, ability: Ability, pos: Vector3) -> integer` | safe | HERO_LIB.count_enemies_in_radius(pos, ability:get_aoe_radius()). Returns 1 when pos is set but the ability has no aoe radius, 0 when pos is nil. |
| `find_auto_victim` | `hx_target.find_auto_victim(ctx: table, aim: table, ability: Ability, opts?: table) -> PlayerPawn\|table\|nil` | safe | Pick the best enemy for an auto-cast sweep per aim.target_mode: SELF→nil, MATE→nearest teammate pick, CLASS (non-"players")→hx_target.pick's class pick (may return a world-target table), ENEMY/default→scan every HERO_LIB.enemies(), filtering by opts.require_lethal (checked via opts.lethal_check(ability, pawn, seconds), opts.kill_aim + kill_plan, or HERO_LIB.is_lethal), optionally gating each candidate by aim_point + can_cast when opts.gated, then preferring visible candidates with the lowest HP; opts.sticky_idx strongly favours the previous target. |
| `force_head_aim` | `hx_target.force_head_aim(ctx: table, aim: table, target: any) -> Vector3\|nil` | safe | HERO_LIB.get_hitbox_aim(target, FORCE_HEAD) when LOS from the cast origin to that point is clear via HERO_LIB.no_obs_to_pos; otherwise the user-configured hitbox aim (encoded from aim.hitboxes), otherwise the head position (even without LOS), otherwise HERO_LIB.get_target_pos. nil when target is not a pawn. |
| `force_hitbox` | `hx_target.force_hitbox(slot1based: integer) -> integer` | safe | Hitbox bit mask that pins selection to exactly one hitbox: sets both the enable bit and the priority bit for the 1-based HITBOX slot (HITBOX.HEAD..HITBOX.LEGS). FORCE_HEAD equals force_hitbox(HITBOX.HEAD). |
| `helper_pawn` | `hx_target.helper_pawn(ctx: table) -> PlayerPawn\|nil` | safe | HERO_LIB.find_helper_target(ctx.cmd, ctx.lp) cached on ctx.helper_target for the current call chain, then returned as a pawn. ctx.helper_target of false is remembered as "no helper" and skips the lookup; nil when the resolved target is not a pawn. |
| `hitbox_bits` | `hx_target.hitbox_bits(hitboxes: table) -> integer` | safe | Pack a 5-entry hitboxes array into 10 bits: the low 5 bits enable each slot (array value >= 1), the high 5 bits mark it priority (value >= 2). Returns 0 when hitboxes is nil. |
| `item_in_slot` | `hx_target.item_in_slot(lp: PlayerPawn, item_index: integer) -> Ability\|nil` | safe | lp:get_ability_by_slot(4 + item_index). item_index must be a number (nil / non-number returns nil); no range check — the engine returns nil for slots that are not real. |
| `kill_plan` | `hx_target.kill_plan(aim: table, ability: Ability, target: any, seconds?: number) -> table\|nil` | safe | Query HERO_LIB.lethality(ability, pawn, seconds or 0) and pick a hitbox plan that one-shots: returns { bone="head"\|"body", bits, dmg } when a permitted hitbox set deals >= target hp — preferring head when it is both enabled and priority in aim.hitboxes, else body (hitboxes minus head/neck), else head as a last resort. Falls back to head+neck+torso when hitboxes is empty. nil for missing inputs, non-number seconds, invalid lethality, hp <= 0, or when nothing is lethal. |
| `line_clear` | `hx_target.line_clear(from: Vector3, to: Vector3, pawn: PlayerPawn) -> boolean` | safe | trace.cast(from, to, LINE_FILTER). True when the trace fraction is >= 0.97, or when it hit pawn itself at fraction > 0 (pawn's own hitboxes do not block a shot aimed at them). False on nil trace or any other blocker. |
| `pick` | `hx_target.pick(ctx: table, aim: table, mode_override?: integer, ability?: Ability) -> any,string\|nil` | safe | Pick a target per aim.target_mode (overridable with mode_override). SELF→ctx.lp, nil. MATE→nearest alive teammate within aim.mate_min_hp_pct/mate_max_hp_pct and aim.mate_max_fov (defaults 180°), nil. CLASS→HERO_LIB.entities_by_class(aim.target_class, …) wrapped as a world target, with reasons "class-unset" (missing slug, warned once), "class-unknown" (slug not registered, warned once) or "class-none" (empty rows); "players" slug falls through to enemy pick. Default ENEMY→HERO_LIB.find_combo_target with max_range from aim.max_range_m or the ability cast range (sentinel-capped by RANGE_SENTINEL_U, else ctx.combo_tcfg.max_range_m, else 1e6 m), FOV from aim.max_fov tightened by ctx.combo_tcfg.combo_fov, visibility aim.require_visibility != false, priority ctx.combo_tcfg.priority; falls back to the closest acceptable enemy from HERO_LIB.get_heroes_in_radius if the combo pick is rejected. |

### hx_aim

`table` · tier `safe` — Per-slot aim resolution: effective aim mode, hitboxes array, point mode, headshot cap and distance-scaled FOV. Values come from per-ability HeroCfg slugs ("script/aim_type", "script/hitbox_*", …) and are memoised per tick. Load it with local Aim = require("hx_aim").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `POINT` | `.POINT: table` | safe | Per-slot point-mode ids read from "script/point_mode": HITBOXES=0, BONE=1, HEIGHT=2, SURFACE=3, ORIGIN=4. |
| `effective` | `hx_aim.effective(slot0: integer, aim: table) -> table` | safe | Return a per-tick cached shadow of aim (via __index) with .mode and .hitboxes already resolved for slot0. Keyed by (slot, aim) with the aim table as a weak key; recomputed when U.tick() advances. Non-table aim is returned as-is. Marks the shadow with __slot so slot_of() can read the slot back; also logs a one-shot [aim] twins line in dev mode. |
| `hitboxes` | `hx_aim.hitboxes(slot0: integer, aim: table) -> table` | safe | Resolve a 5-entry hitboxes array for the slot. If aim.hitboxes equals the ability default [1,1,1,0,0], reads per-slot "script/hitbox_head/neck/torso/arms/legs" and floor-clamps each to 0..2 (unset slots fall back to the ability default). Otherwise uses aim.hitboxes directly. Finally applies the headshot cap: when "script/headshot_cap" is true and HERO_LIB.headshot_cap_ok("script/max_headshots" or 23%) is false, zeros the head and neck slots, promoting torso to 1 if nothing else remains. |
| `mode` | `hx_aim.mode(slot0: integer, aim: table) -> integer` | safe | Resolve the effective aim mode. aim.mode == DISABLED stays DISABLED. Otherwise reads per-slot "script/aim_type"; 1→NORMAL, 2→PSILENT, 3→HYBRID. When the per-slot value equals the menu base (nobody has twinned it), aim.mode wins; when it differs the per-slot value wins. Falls back to aim.mode or HYBRID when the slug is unset. |
| `point_mode` | `hx_aim.point_mode(slot0: integer) -> integer` | safe | Per-slot "script/point_mode" floored to an integer and clamped to the POINT.* range (returns POINT.HITBOXES for out-of-range or unset values). |
| `resolve_point` | `hx_aim.resolve_point(slot0: integer, target: any, bits: integer) -> Vector3\|nil` | safe | HERO_LIB.resolve_aim_point(target, opts) with per-slot opts: mode from point_mode(slot0), bits as given, bone from "script/point_bone" when mode is BONE (returns nil if unset or empty), z from "script/point_z" (default 0.0) when mode is HEIGHT. Reuses one shared options table — do not retain the engine's view of it. |
| `scale_fov` | `hx_aim.scale_fov(slot0: integer, base_fov: number, dist_m: number) -> number` | safe | Distance-scaled FOV. Returns base_fov unchanged when "script/distance_scaled_fov" is false, or base_fov is not a positive number, or dist_m is not a number. Otherwise lerps between base_fov at or below "script/fov_full_distance" (default 8 m) and base_fov * clamp("script/fov_far_scale"*0.01, 0.01..1.0) at or above "script/fov_min_distance" (default 30 m), with "script/fov_scale_curve" (minimum 0.05) as the lerp exponent. If far <= near+0.1 it is bumped to near+0.1 to avoid a divide-by-zero. |
| `slot_of` | `hx_aim.slot_of(aim: table) -> integer` | safe | rawget(aim, "__slot") when it is a valid slot 0..3, else -1. Reads only the shadow tables produced by effective(); plain aim configs will always return -1. |
| `type_bits` | `hx_aim.type_bits(mode: integer) -> integer` | safe | Encode a Cfg.AIM mode into aim.type bits: NORMAL→DEFAULT, PSILENT→SILENT, HYBRID→DEFAULT\|SILENT, anything else→0. |

### hx_vis

`table` · tier `safe` — Snapshot and render-thread drawing helpers for hero scripts: builds the per-tick snapshot that feeds the HUD, drives the kill indicator and 3D kill markers, and offers thin 2D line/point/path wrappers over Render.*. Load it with local Vis = require("hx_vis").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ability_killable` | `hx_vis.ability_killable(ctx: table, ab: Ability, out: table)` | safe | Appends the index of every alive, targetable enemy that ab would kill right now into out. Walks HERO_LIB.enemies() through the kill_rows reach gate, feeds predicted damage into kill_damage, and uses ability_lethal for the final decision. nil ab or a kill_rows gate that returns nil is a silent no-op; HERO_LIB.is_ability_in_cd(ab) sets the cooling flag. |
| `ability_lethal` | `hx_vis.ability_lethal(ab: Ability, pawn: PlayerPawn, L?: table\|boolean) -> boolean` | safe | True when ab would kill pawn now. If L is nil the function computes HERO_LIB.kill_lethality(ab, pawn, 0) first; if L is a table with valid=true and lethal=true it returns true outright; otherwise it falls back to HERO_LIB.engine_execute(ab, pawn)==true. Pass L=false to skip the lethality lookup and go straight to engine_execute. |
| `any_lethal` | `hx_vis.any_lethal(ab: Ability) -> boolean` | safe | True if ability_lethal(ab, e) is true for any alive, non-untargetable enemy returned by HERO_LIB.enemies(). |
| `begin` | `hx_vis.begin(ctx: table, into?: table, fresh_hero?: boolean) -> table` | safe | Starts a per-tick hero snapshot and returns it. Without into it allocates { hero_id=ctx.cfg.hero_id, now=ctx.now, combo_active=false, targets={}, hero={} }. With into it reuses the same table: restamps hero_id/now, clears combo_active, empties targets in place, and replaces into.hero with a fresh table only when fresh_hero is truthy or into.hero was nil. |
| `begin_kill_3d` | `hx_vis.begin_kill_3d(ctx: table, hero_id: integer)` | safe | Resets the shared 3D kill-marker buffer for (ctx.tick, hero_id). A second call with the same tick+hero_id pair is a no-op, so sibling features sharing a slot keep each other's push_kill_3d entries. |
| `can_kill_indicator` | `hx_vis.can_kill_indicator(ctx: table, slot: integer, killable?: function)` | safe | Throttled HUD kill-indicator refresh for slot: runs at most every 0.05 s per slot, with a 0.25 s grace that keeps the previous markers after any reach was last observed, then publishes via HERO_LIB.set_can_kill_indicator. Fills the shared KILLABLE/REACH scratch tables by calling killable(ctx, out) when provided, else slot_killable(ctx, slot, out). The next_by_slot / grace_by_slot timers are stashed on ctx.hero.ck_next_by_slot / ck_grace_by_slot. |
| `clear` | `hx_vis.clear()` | safe | Drops the published snapshot, zeroes the 3D kill-marker count, and hides the native draw-target marker if a previous publish had shown one. |
| `draw_killable_markers_3d` | `hx_vis.draw_killable_markers_3d(hero_id: integer)` | safe | Draws an orange chevron above each pawn pushed with push_kill_3d. No-op when hero_id does not match the buffer or the buffer is more than two engine ticks stale. Alpha drops to 102/255 for pawns that were not visible when pushed; the markers bob with HERO_LIB.game_time(). |
| `draw_line` | `hx_vis.draw_line(a: Vector3, b: Vector3, color: Color)` | safe | Render.Line between the screen projections of a and b. Silent when either endpoint is nil or does not project. |
| `draw_path` | `hx_vis.draw_path(path: table, color: Color)` | safe | Render.Line segments through each consecutive pair of Vector3 entries in path. A non-table path is a silent no-op; individual segments whose endpoints fail to project are skipped. |
| `draw_point` | `hx_vis.draw_point(v: Vector3, color: Color)` | safe | Render.FilledCircle of radius 5 at v:ToScreen(). Silent when v is nil or does not project. |
| `kill_damage` | `hx_vis.kill_damage(pawn: Entity, damage: number)` | safe | Records the predicted damage for pawn into the active can_kill_indicator reach row. No-op unless a can_kill_indicator pass is currently collecting and damage is a number; silently exits if pawn is not already in the reach list. |
| `kill_feature` | `hx_vis.kill_feature(o: table) -> table` | safe | Builds a hero-descriptor feature table that drives the kill indicator each tick. o: { key, label, slot, killable?, blurb?, when? }. The returned feature has default=false, bind=true, casts=false, indicator=true, runs_during_combo=true and an on_tick that calls can_kill_indicator(ctx, o.slot, o.killable). If blurb is omitted a generic one is composed from label and the when phrase (default "it hit"). |
| `kill_in_reach` | `hx_vis.kill_in_reach(rows: table, pawn: Entity, pos?: Vector3) -> boolean` | safe | Reach gate using the fields on a kill_rows table (visible_only, max_u, origin). pos defaults to pawn:get_origin(). While a can_kill_indicator pass is collecting it also records up to 32 reach-row pawn indices (damage 0; overwrite later via kill_damage). |
| `kill_rows` | `hx_vis.kill_rows(ctx: table, ab: Ability, cooling: boolean) -> table\|nil` | safe | Returns a shared, mutable rows table { visible_only, max_u, origin } built from the HeroCfg kill/* native keys and ctx.lp:get_origin(). nil when cooling is true but KILL_ON_COOLDOWN is not enabled, or when KILL_UPGRADED is required and ab has no upgrade bits. The same table instance is reused across calls. |
| `mark_target` | `hx_vis.mark_target(S: table, ctx: table, slot0: integer, target: Entity\|nil, aim_pos?: Vector3)` | safe | Appends a draw-target highlight entry to S.targets for slot0. No-op when both target and aim_pos are nil, when Cfg.show_combo_target is off, or when the slot's aim has no draw_target flag. Position is aim_pos or U.origin_of(target); the entry's rgba defaults to r=1, g=0.3, b=0.32, a=1 before aim.target_color overrides each channel. |
| `publish` | `hx_vis.publish(S: table, trusted?: boolean) -> boolean` | safe | Validates S and publishes it as the current snapshot. Validation requires a numeric S.hero_id and only plain scalar/Vector userdata keys/values down to depth 6 (no live handles); it is skipped on non-dev builds when trusted is true. On success it stores S and iterates S.targets to push the first entry with a valid index into HERO_LIB.set_draw_target, or hides the previously shown marker if there is none. Returns false and logs on validation failure. |
| `push_kill_3d` | `hx_vis.push_kill_3d(pawn: PlayerPawn)` | safe | Appends a head-position entry to the current 3D kill-marker buffer. Uses HERO_LIB.get_hitbox_aim with the head bone bits when available, else pawn:get_origin() lifted by 72 units. Records pawn:is_visible() for the alpha ramp. Silent for a nil pawn or when neither hitbox nor origin is available. Entries are pooled and reused across ticks. |
| `reach_meter` | `hx_vis.reach_meter(text: string, n: number, full?: number)` | safe | Draws a centred text panel low on the screen (y = 885/1080 of screen height) with a shadow and main_background background. When full is given, the ink colour lerps from primary_widgets_text toward the primary style colour as min(n, full)/full approaches 1. |
| `slot_killable` | `hx_vis.slot_killable(ctx: table, slot: integer, out: table)` | safe | Convenience: ability_killable(ctx, Tgt.ability_in_slot(ctx.lp, slot), out). |
| `snapshot` | `hx_vis.snapshot(hero_id?: integer) -> table\|nil` | safe | Returns the last snapshot that publish() accepted, or nil. When hero_id is given, also returns nil if the stored S.hero_id does not match (stale-hero guard). |

### hx_cast

`table` · tier `safe` — Projectile autofire framework: factory for cast steps with combo and assist entry points, ground-autocast helpers, and a few shared predict/aim utilities. Load it with local Cast = require("hx_cast").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ALT_AIM` | `.ALT_AIM: table` | safe | Shared aim preset for alt-fire style casts: { mode = Cfg.AIM.NORMAL, mouse_smooth_x = 35, mouse_smooth_y = 35 }, with a metatable that falls back to Steps.DEFAULT_AIM for any field left unset. |
| `ALT_READY_CODES` | `.ALT_READY_CODES: table` | safe | Ready-code allow-list { "ECitadelAbilityOrder_Invalid_Hidden" } to pass through HERO_LIB.is_ability_ready for abilities whose alt-fire reports Invalid_Hidden while otherwise ready. |
| `GROUND_CHAIN_KEYS` | `.GROUND_CHAIN_KEYS: table` | safe | Condition keys consumed by HERO_LIB.get_ground_autocast_remaining: { "stun", "victor_revive", "rejuvenator", "doorman_hotel", "void_sphere", "shadow_transformation" }. Index-matched to GROUND_CHAIN_STATES. |
| `GROUND_CHAIN_STATES` | `.GROUND_CHAIN_STATES: table` | safe | Human-readable labels for the condition set in GROUND_CHAIN_KEYS, same order: { "Stunned", "Shocking Reanimation", "Rejuvenator", "Hotel Guest", "Quantum Entanglement", "Shadow Transformation" }. |
| `combo_step_at` | `hx_cast.combo_step_at(ctx: table, caster: table, step: table, pawn: PlayerPawn) -> integer` | safe | Calls caster.combo_step(ctx, step) with ctx.target temporarily overridden to pawn, restores the previous ctx.target on return, and hands back the Steps verdict the caster chose. |
| `ground_aim_pos` | `hx_cast.ground_aim_pos(enemy: PlayerPawn, dest: Vector3\|nil, protected: boolean, ab: Ability, origin: Vector3, range: number) -> Vector3\|nil` | safe | Picks a ground-cast aim position: dest when given, otherwise enemy:get_origin(). When protected it re-projects the point through HERO_LIB.project_ground_autocast_position for ab. Returns nil when the chosen point is further than range from origin. |
| `ground_landing` | `hx_cast.ground_landing(pawn: PlayerPawn, secs: number) -> Vector3\|nil` | safe | Returns HERO_LIB.simulate_movement_for_duration(pawn, secs + 2*interval + latency), or nil when pawn is on a zipline or the simulation ends airborne (not grounded). |
| `ground_remaining` | `hx_cast.ground_remaining(enemy: PlayerPawn, cond: string) -> number, boolean, Vector3\|nil` | safe | Thin wrapper over HERO_LIB.get_ground_autocast_remaining(enemy, cond). Returns remaining seconds (0 when the native returned nil), a protected flag, and the predicted destination (or nil if the native did not give one). |
| `ground_settle` | `hx_cast.ground_settle(pawn: PlayerPawn, pos: Vector3, protected: boolean, ab: Ability, landing: function, secs: number) -> Vector3\|nil` | safe | Settles pos into a stable ground-cast point. Returns pos unchanged when protected. Otherwise if pawn has any velocity it first calls landing(pawn, secs) to predict a stop; then if pawn is still not on_ground it re-projects via HERO_LIB.project_ground_autocast_position. nil when pawn:get_velocity() is unavailable or landing returned nil. |
| `hittable` | `hx_cast.hittable(pawn: PlayerPawn) -> boolean` | safe | True when pawn:valid() and pawn:is_alive() and not HERO_LIB.is_out_of_game(pawn) and not HERO_LIB.is_invulnerable(pawn). |
| `projectile` | `hx_cast.projectile(o: table) -> CastProjectile` | safe | Builds and returns a CastProjectile object whose combo_step, assist, draw, last_cast and step closures all share the option table o. Required keys depend on usage: slot (0..3) OR bits for a slotless caster, feature_key for the persistent step key, usually ability (name string or resolver fn), plus any of aim, cast_point, cast_range, hull/hull_radius, lift_u, gap_ticks, max_range_m, lands_only, manual_helper, solve, alt_cast, hold, probe, target_ok, manual_passthrough, smooth, fire_when, predict, ready_codes, pick_fallback, needs_aim. A caster built with bits must also set ability; the function errors otherwise. |
| `user_pressing` | `hx_cast.user_pressing(cmd: table, bit: integer) -> boolean` | safe | True when any of cmd.button_state0 / button_state1 / button_state2 has the given input bit set this tick. |

### CastProjectile

`table` · tier `safe` — Returned by hx_cast.projectile(o). Carries the per-feature combo_step, assist, draw, last_cast and step closures bound to its option table.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `assist` | `:assist(ctx: table)` | safe | Autofire tick entry point. Loads (or creates) the persistent assist step under ctx.hero[feature_key.."_cast_step"], resolves the current fires_when policy, gates combo / free-cursor / native-manual and cooldown, picks a target (helper_pawn first, then ctx.target, then a Tgt.pick fallback for autonomous modes), auto-upgrades Aim Disabled to a safe PSilent variant where allowed, and runs the shared aim+fire pipeline. No return value; faults and gating decisions are logged on dev builds. |
| `combo_step` | `:combo_step(ctx: table, step: table) -> integer` | safe | Combo-step entry point. Returns a Steps verdict (COMPLETE / WAIT / HOLD / SKIP). For slotless casters delegates to the shot-step path (arm, pick target, aim). For slotted casters it tracks cast-delay/mark, promotes Aim Disabled to a safe PSilent variant when needed, runs the predict+hull chain, honours manual_passthrough, and returns HOLD while a cast is under way. |
| `draw` | `:draw()` | safe | Dev-only debug overlay: draws the last predicted target path (red), projectile path (yellow) and aim point (green). The field is nil on non-dev builds; even on dev builds the function returns immediately unless HERO_LIB.dev_mode() is true. |
| `last_cast` | `:last_cast(src: table) -> table\|nil` | safe | Returns a shared view table { mark, pawn, at } describing the last cast marked by this caster, or nil when no mark or cast_pawn is live. src may be the persistent step itself, or any table with a .hero map (then the function looks up src.hero[feature_key.."_cast_step"]). The same cast_view instance is overwritten on each call. |
| `step` | `:step(ctx: table) -> table\|nil` | safe | Returns ctx.hero[feature_key.."_cast_step"] — the persistent step state table for this caster — or nil when assist() has not yet created it for this hero. |

### hx_registry

`table` · tier `safe` — Hero descriptor registry: register(), look up and fault-budget hero hooks, and host feature calls. Load it with local Reg = require("hx_registry").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `caller` | `hx_registry.caller(H: table\|nil) -> RegistryCaller` | safe | Returns a RegistryCaller bound to descriptor H. Nil H yields a null caller whose call() always returns nil. The caller is cached on H._caller, so repeated requests return the same object. |
| `count` | `hx_registry.count() -> integer` | safe | Number of hero descriptors currently in the registry. |
| `feature_call` | `hx_registry.feature_call(H: table, feat: table, name: string, ...: any) -> any\|nil` | safe | Invokes feat[name](...) under a per-feature error budget keyed by "feat:<feat.key>:<name>" (3 faults inside a 5 s window, then disabled on H for the session). Returns nil for a nil H, a non-table feat, a missing method, or when the budget is already dead; the fault key cache is weak on feat, so dropped features reclaim their budget entries. |
| `for_hero` | `hx_registry.for_hero(hero_id: integer) -> table\|nil` | safe | Returns the registered descriptor for hero_id. Lazily registers a bare default descriptor (name taken from HeroCfg.current_hero() when its id matches, otherwise "hero <id>") when no explicit register() has run. Returns nil when hero_id is not a positive number. |
| `register` | `hx_registry.register(H: table) -> table` | safe | Validates and registers a hero descriptor. Asserts a numeric H.hero_id, rejects unknown hook names against the fixed whitelist (on_load / on_tick / on_combo_begin / on_combo_end / resolve_slot / should_skip / cooldown_grace / custom_cast / on_step_abandoned / on_before_cast / on_after_cast / on_steer / on_snapshot / on_draw), and errors when any press[slot] spec would never press that slot's own ability bit (bs3 is a release edge and never casts). Drops malformed feature entries with a log. Freezes press/options/hooks/features, initialises H.faults and H.state, replaces any previous descriptor for this hero_id (logged as a hot reload), calls Opts.reset(hero_id), then calls H.hooks.on_load(H) if present. Returns H. |
| `reset_state` | `hx_registry.reset_state(hero_id?: integer)` | safe | Clears .state and .faults on the registered descriptor for hero_id, or on every descriptor when hero_id is nil. Does not touch hooks/press/options. |

### RegistryCaller

`table` · tier `safe` — Returned by hx_registry.caller(H). Invokes a named hook on H under a per-key error budget (3 faults in 5 s then disabled for the session).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `call` | `:call(name: string, ...: any) -> any\|nil` | safe | Invokes H.hooks[name](...) under a per-hook error budget keyed by name (3 faults inside a 5 s window, then DISABLED for the session). Returns the hook's result, or nil when the hook is missing, the budget is dead, or the call errored (traceback logged). |

### hx_bus

`table` · tier `safe` — Psilent aim bus wrappers: a single request/steer entry point over HERO_LIB.aim_psilent_default plus settled/reach_ok/aim_on_target helpers. Load it with local Bus = require("hx_bus").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `BUSY` | `.BUSY: string` | safe | The literal string "busy". request() returns this when cmd or pos is missing, or when a psilent request ran but did not fire this tick. |
| `FIRED` | `.FIRED: string` | safe | The literal string "fired". request() returns this when the underlying HERO_LIB.aim_psilent_default call invoked the on_fire callback. |
| `PENDING` | `.PENDING: string` | safe | The literal string "pending". request() returns this when psilent was off and no fire happened this tick. |
| `aim_on_target` | `hx_bus.aim_on_target() -> boolean` | safe | Thin wrapper over HERO_LIB.script_aim_on_target(): true when the current script-driven aim is pointed at the target. |
| `reach_ok` | `hx_bus.reach_ok(lp: PlayerPawn, cmd: table, pos: Vector3, scope: string) -> boolean` | safe | Wraps HERO_LIB.psilent_reach_ok(lp, cmd, pos, scope). A nil pos short-circuits to false. |
| `request` | `hx_bus.request(req: table) -> string` | safe | Runs HERO_LIB.aim_psilent_default from a request table and returns one of FIRED / PENDING / BUSY. Fields: cmd, pos, target, smooth (default 0), radius (default 0), ability, psilent (falsy = non-psilent aim; truthy = silent, with .drive truthy selecting drive mode 2 and otherwise plain true), should_cancel (continue predicate), on_fire (callback). Missing cmd or pos returns BUSY immediately. Returns FIRED if on_fire was invoked, else BUSY when psilent was truthy, else PENDING. The outer in-flight request is saved and restored across the call so requests can nest. |
| `settled` | `hx_bus.settled() -> boolean` | safe | Thin wrapper over HERO_LIB.psilent_bus_settled(): true when the aim bus has no pending psilent transition. |
| `steer_normal` | `hx_bus.steer_normal(cmd: table, pos: Vector3, opts?: table) -> boolean` | safe | Non-firing steer: aims toward pos without issuing a cast. opts may include smooth (default 0), target, radius (default 0), cancel (continue predicate), ability. Returns false when cmd or pos is nil, otherwise returns true after running HERO_LIB.aim_psilent_default in non-psilent mode. The current opts are stacked around the call so steer_normal can nest. |
| `steer_view` | `hx_bus.steer_view(cmd: table, pos: Vector3, target?: PlayerPawn, ability?: Ability, smooth?: number)` | safe | Convenience over steer_normal that stuffs target/ability/smooth into a shared VIEW_STEER table before the call and clears target/ability afterward. radius defaults to 0 and cancel is never set, so the steer always continues. |

### hx_chess_board

`table` · tier `safe` — Chess Master bishop/queen grid-search, trace-budget and lob-deployment helpers. Load it with local ChessBoard = require("hx_chess_board").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `PIECE_CLASS` | `.PIECE_CLASS: string` | safe | vdata class name of a chess piece ("CNPC_ChessPiece"); used to recognise pieces during world traces. |
| `PIECE_QUEEN` | `.PIECE_QUEEN: integer` | safe | m_iChessPieceType value that marks the queen (1). |
| `PIECE_BISHOP` | `.PIECE_BISHOP: integer` | safe | m_iChessPieceType value that marks a bishop (2). |
| `DEPLOY_NEAR_U` | `.DEPLOY_NEAR_U: number` | safe | Vertical bias (~187u, i.e. about 6 metres) added to launch-vs-target height when solving the deployment lob's discriminant. |
| `ZERO` | `.ZERO: Vector3` | safe | Vector3(0, 0, 0) exported for reuse by callers. |
| `GROUND_OFFSET` | `.GROUND_OFFSET: Vector3` | safe | Vector3(0, 0, 40); vertical offset the lib adds to a cell before dropping a trace onto the ground. |
| `angle_dist` | `hx_chess_board.angle_dist(a: Angle, b: Angle) -> number` | safe | Euclidean distance between two angles over (pitch, yaw, roll). Yaw difference goes through utils.angle_diff so wraparound is handled. |
| `attack_reach` | `hx_chess_board.attack_reach(bishop: Ability) -> number\|nil` | safe | Total 2D reach of a bishop attack: MoveDistance + 100 + sqrt(2)*(floor(TileSteps)*100 + 50). nil when MoveDistance or TileSteps is missing or MoveDistance <= 0. |
| `auto_in_area` | `hx_chess_board.auto_in_area(bishop: Ability, piece: Entity, target: Entity) -> boolean` | safe | 2D circle check: true when target's origin is within attack_reach(bishop) of piece's origin. false when any origin or the reach is missing. |
| `budgeted` | `hx_chess_board.budgeted(pool: string, tick: integer, solve: any, ...: any) -> any` | safe | Runs solve(...) under this lib's per-tick trace quota. pool is "rook" or "piece"; both quotas reset when tick changes. Returns nil immediately if the pool is already exhausted, and returns nil (discarding solve's results) if any line/sweep call during solve runs the pool out mid-solve. Otherwise forwards solve's return values. |
| `current_destination` | `hx_chess_board.current_destination(lp: PlayerPawn, cmd: table, move: Ability, piece: Entity, bits: integer, aimed: Angle) -> Vector3\|nil` | safe | Resolves the world destination a bishop move command would snap to right now: picks the aim angle (aimed when bits has aim.type.SILENT, otherwise the command's camera angles), projects it through range, caps by the ability's MoveDistance, applies the move's m_bSweepToDestination, and grid-snaps onto the chess board. nil when any input (origin, bounds, range, vdata, aim projection) is missing. |
| `deployment_cell` | `hx_chess_board.deployment_cell(camera: Vector3, launch: Vector3, forward: Vector3, range: number) -> Vector3\|nil` | safe | Projects aim forward from camera up to the given horizontal range, refines against world geometry, and if the hit isn't roughly flat ground probes ~85u forward-and-sideways; then drops to ground and snaps to the nearest 100u cell centre. nil when forward is horizontal-flat, range is non-positive, or any trace fails. |
| `deployment_landing` | `hx_chess_board.deployment_landing(bishop: Ability, launch: Vector3, forward: Vector3, predicted: Vector3, range: number) -> Vector3,number\|nil` | safe | Simulates the bishop deployment lob: reads speed/gravity-scale/up/vertical-bias/radius from the ability's m_projectileInfo and sv_gravity, caps range by m_flMaxLinearRange, then walks U.interval()-sized ticks until a swept LOB trace hits something, drops that point to the ground, and returns (ground_point + m_flVerticalOffset, time_in_flight). nil on any missing info, non-positive gravity/speed/horizon, out-of-range travel, or trace failure. |
| `movement_solution` | `hx_chess_board.movement_solution(ctx: table, bishop: Ability, move: Ability, piece: Entity, target: Entity, allow_approach: boolean, holding: boolean) -> Vector3,Vector3,Vector3,Vector3,boolean\|nil` | safe | Charges traces to the "piece" pool for ctx.tick and searches the 100u board for the best cell to send the bishop to: builds a preferred lead point from the target's velocity, enumerates reachable same-colour cells, aim-projects each one through the cmd and picks the one whose predicted tile-aura cover is best. Returns (aim_pos, destination, predicted_target, source, pass1) where pass1 is true when the pick came from the strict in-reach pass; nil when no cell qualified or the trace budget ran out. allow_approach enables a second looser pass; holding uses the move's cached distance instead of the bishop's scaled MoveDistance. |
| `queen_cell_allowed` | `hx_chess_board.queen_cell_allowed(cell: Vector3, predicted: Vector3) -> boolean` | safe | true when cell and predicted land in cells whose integer indices differ by at most 1 on both x and y (i.e. within the queen's one-square move). |
| `queen_move_solution` | `hx_chess_board.queen_move_solution(ctx: table, queen: Ability, move: Ability, piece: Entity, target: Entity, approach: boolean, holding: boolean) -> Vector3,Vector3,Vector3,Vector3,boolean\|nil` | safe | Charges traces to the "piece" pool and finds the best cell for the queen to teleport to. With approach false the search is limited to the 3x3 cluster around the target's simulate_future point; approach true opens the full MoveDistance+100 ring and accepts any cell that strictly closes the gap. Returns (aim_pos, destination, future_target, source, close) where close is queen_cell_allowed(destination, future). nil when source/future/range/bounds are missing, the queen is already on the predicted cell, or no cell satisfies the filter. |
| `set_caster` | `hx_chess_board.set_caster(lp: PlayerPawn)` | safe | Stores lp:get_index() and lp:get_team_number() in the lib's trace filter so world/lob should_hit callbacks can skip the local player and (for the lob) the local player's team. Call once before using sweep/current_destination/*_solution with a new local pawn. |
| `simulate_future` | `hx_chess_board.simulate_future(pawn: Entity, duration: number) -> Vector3\|nil` | safe | Asks HERO_LIB.simulate_movement_for_duration(pawn, duration) for a predicted position; when a velocity is also returned, extrapolates it by 2*U.interval() + U.latency() to compensate for the input/net lag. Returns the position only if the sim gives one, else nil. |
| `sweep` | `hx_chess_board.sweep(a: Vector3, b: Vector3, mins: Vector3, maxs: Vector3, f?: table) -> table\|nil` | safe | trace.cast with the lib's default world filter (skips the local pawn and anything with vdata class CNPC_ChessPiece). f overrides the filter. Also decrements the active trace budget inside a budgeted() call; returns nil (and poisons the enclosing budgeted call) when the budget has run out. |
| `tiles_reach` | `hx_chess_board.tiles_reach(destination: Vector3, target_pos: Vector3, steps: integer, height: number, mins: Vector3, maxs: Vector3) -> boolean` | safe | true when a steps-cell 100u-grid tile aura centred on destination overlaps the AABB (mins..maxs) around target_pos, with a vertical gate of +/- height. Pure arithmetic — no traces. |

### hx_blocks

`table` · tier `safe` — Reusable feature-option row builders plus per-tick readers that resolve the chosen values at runtime. Load it with local Blocks = require("hx_blocks").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `CAST_ON` | `.CAST_ON: table` | safe | Enum table for cast_on() option values: { ME = 1, ALLIES = 2 }. |
| `MEASURE` | `.MEASURE: table` | safe | Enum table for the health() measure field: { PCT = 1, HP = 2 }. |
| `TRIGGER` | `.TRIGGER: table` | safe | Enum table for the health() trigger field: { BELOW = 1, LOST = 2, BOTH = 3 }. |
| `allies` | `hx_blocks.allies(a?: table) -> table` | safe | Builds the "allies nearby" option rows: an on/off toggle, a count slider (default 1, max a.max=5), an ally-radius slider in metres (default a.radius_m=10, max a.radius_max_m=30), and a "visible allies only" toggle. All three sub-rows depend_on the first toggle. a may override on, allies, max, radius_m, radius_max_m, visible. |
| `allies_ok` | `hx_blocks.allies_ok(ctx: table, feature_key: string, origin: Vector3) -> boolean,integer` | safe | Evaluates the allies() block for the given feature. Returns (true, 0) when the toggle is off. Otherwise counts allies within the configured radius (converted from metres via U.m_to_u), filters by visibility when allies_visible is set, and returns (count >= needed, count). |
| `cast_on` | `hx_blocks.cast_on(a?: table) -> table` | safe | Builds a single multi-select "Cast on" row with choices { "Me", "Allies" } and a default list derived from a.me (default true) and a.allies (default false), using CAST_ON indices. |
| `chain` | `hx_blocks.chain(a: table) -> table` | safe | Builds the chaining-into-states rows: a multi-select over a.states (required), "After it ends" and "Early by" millisecond sliders, and a "Chain disables" toggle. Defaults: all states selected (a.default overrides), after_ms a.after_ms=60 (0..500), early_ms a.early_ms=250 (0..1000), chain a.chain=true. Errors when a.states is missing. |
| `crowd` | `hx_blocks.crowd(a?: table) -> table` | safe | Builds the "enemies in area" option rows: an enemies-needed slider (default a.enemies=2, max a.max=6) and a "visible enemies only" toggle (default a.visible=false). |
| `crowd_ok` | `hx_blocks.crowd_ok(ctx: table, feature_key: string, origin: Vector3, radius_u: number) -> boolean,integer` | safe | Evaluates the crowd() block for the given feature. Counts enemies in a radius_u ball around origin (through HERO_LIB.enemies_in_radius + visibility filter when enemies_visible is set, otherwise the fast count). Returns (count >= needed, count); needed defaults to 1. |
| `health` | `hx_blocks.health(a?: table) -> table` | safe | Builds the self-health trigger rows: a trigger enum (Health below / Health lost / Both), a measure enum (% / HP), two below-health sliders (one per measure), two health-lost sliders (one per measure), and a loss-window seconds slider that appears unless trigger is set to BELOW. All defaults come from the matching keys in a (trigger, measure, below_pct, below_hp, loss_pct, loss_hp, window_s). |
| `health_due` | `hx_blocks.health_due(ctx: table, feature_key: string, pawn?: PlayerPawn) -> boolean` | safe | Evaluates the health() block against pawn (defaults to ctx.lp). Returns false when hp or max_health is non-positive. Otherwise checks the below-health arm (when trigger != LOST) in either % or HP, then the health-lost arm (when trigger != BELOW) over the configured window via HERO_LIB.damage_taken. true as soon as either arm fires. |
| `items` | `hx_blocks.items(a: table) -> table` | safe | Builds a single multi-select item picker. Requires a.items (choice list) and a.key (option key); label defaults to the key, default to all indices, tooltip is passed through from a.tooltip. |
| `join` | `hx_blocks.join(...: table) -> table` | safe | Concatenates several option-row lists into one, in order. When two rows share the same non-nil key the second is dropped and the lib logs "hx_blocks: option key '%s' appears twice in one feature; the second is dropped". |
| `lands` | `hx_blocks.lands(a?: table) -> table` | safe | Builds a single "Only when it lands" toggle row with default a.default=true. |
| `lethal` | `hx_blocks.lethal(a?: table) -> table` | safe | Builds a single "Only if it would kill" toggle row (key lethal_only) with default a.default=true. |
| `read` | `hx_blocks.read(feature_key: string) -> table` | safe | Returns a per-feature reader table that resolves feature.value(feature_key, name) on __index. The cache is flushed at the start of every U.tick(), nil values are memoised, and __newindex errors — the table is read-only. The same proxy table is reused across calls for one feature_key. |
| `reach_meter` | `hx_blocks.reach_meter(a?: table) -> table` | safe | Builds the "Show enemies in reach" meter rows: a master toggle plus "While on cooldown" and "Only while casting" dependent toggles. Default of the master toggle comes from a.default (default false). |
| `save_defaults` | `hx_blocks.save_defaults(o: table) -> table` | safe | Returns a baseline settings table for a "save ally" style ability: carries over o.targets, o.aim, o.target_filter, o.self_only, o.max_fov (default 30), and seeds triggers={health=true, health_loss=false} with 30%/300HP below and 20%/200HP lost over 1.0s defaults. |
| `save_settings` | `hx_blocks.save_settings(ctx: table, feature_key: string, slot0: integer, s: table, default_mode: string) -> table` | safe | Mutates and returns the save-ability settings table s with the current values of the health() and cast_on() blocks (triggers, mode strings, thresholds, loss window). When s.self_only is already true, exits before touching targets/aim. Otherwise copies the cast_on picks into s.targets.self/allies, resolves the effective aim via hx_aim.effective(slot0, hx_cfg.aim(ctx.cfg, slot0)), writes s.max_fov from b.aim_fov_deg (or the aim's max_fov, else 30), and sets s.aim.type to 0 when ctx.no_script_aim[slot0] is true else Aim.type_bits(aim.mode or default_mode), with s.aim.smooth from aim.mouse_smooth_x (default 35). |
| `with` | `hx_blocks.with(rows: table, fields: table) -> table` | safe | Shallow-copies every key/value in fields onto every row in rows (mutating in place) and returns rows. Used to tag a block's rows with shared attributes like category or role. |

### hx_close_in

`table` · tier `safe` — Melee gap-closer helpers: cone/line-of-sight verdicts and Warp Stone / Phantom Strike pick-and-use. Load it with local CloseIn = require("hx_close_in").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ITEMS` | `.ITEMS: table` | safe | Array of the item tokens this lib supports, in picker order: { "upgrade_warp_stone", "upgrade_phantom_strike" }. |
| `PHANTOM_STRIKE` | `.PHANTOM_STRIKE: string` | safe | Phantom Strike item token ("upgrade_phantom_strike"). |
| `WARP_STONE` | `.WARP_STONE: string` | safe | Warp Stone item token ("upgrade_warp_stone"). |
| `ability_fov` | `hx_close_in.ability_fov(aim: table) -> number\|nil` | safe | Returns aim.max_fov when it is a number strictly between 0 and 180, else nil. Convenience helper for pulling a usable cone-FOV out of an aim config. |
| `cone_decide` | `hx_close_in.cone_decide(ctx: table, step: table, spec: table, verdict: string, autonomous?: boolean) -> any` | safe | Routes a cone_verdict to a Steps result. Delivers (via spec.deliver) when verdict=="aim" and Steps.aim_off(ctx,step) is false, tagging the step role as offense_assist for manual/helper sources. For manual/helper sources on other verdicts it short-circuits through press_now (or sets skip_reason="own-press" / "out-of-range" / "no-target" with hold=true when lands_only is on). For autonomous callers: "cone" presses now, "far" waits with reason "reach", "aim" waits with reason "fov", "blocked" skips with "los", anything else skips with "no-target". |
| `cone_verdict` | `hx_close_in.cone_verdict(ctx: table, ab: Ability, target: Entity, cone: table, reach_u?: number) -> string,Vector3\|string` | safe | Classifies a target against an ability's cone. Returns ("none") when the target's cast-origin point is unavailable or ctx.lp has no cast origin; ("blocked", pos) when LOS fails; ("far", pos) when reach_u is set and the lp->pos distance exceeds it; ("cone", pos) when within_ability_cone is true; otherwise ("aim", pos). |
| `engage` | `hx_close_in.engage(ctx: table, step: table, ability: Ability, pos: Vector3, reach: string, warp: Ability, strike: Ability, prio: any) -> boolean` | safe | Returns true only when reach=="in" and HERO_LIB.within_ability_cone(ability, pos, {scale=0.7}) says so. For reach "warp"/"both" with pos within 1.15deg FOV it leases prio and queues the warp item; for reach "strike"/"both" with pos inside strike's 0.7-scale cone it leases and queues the strike item. The in-flight item cast is tracked on step.state.item_mark and left pending until Steps.cast_outcome resolves it. |
| `hold_off` | `hx_close_in.hold_off(ctx: table, step: table, why: string, can_wait: boolean) -> any` | safe | When step.source=="manual" presses now (press_now). When can_wait is true and the source is not "helper" writes step.wait_reason=why and returns Steps.WAIT. Otherwise writes step.skip_reason=why and returns Steps.SKIP. |
| `items` | `hx_close_in.items(ctx: table, picks: table) -> Ability\|nil,number,Ability\|nil,number` | safe | Resolves the Warp Stone and Phantom Strike item abilities when the matching picks index (1 and 2) is truthy and HERO_LIB.is_ability_ready returns true. Returns (warp, warp_u, strike, strike_u) where warp_u is the raw cast range and strike_u is max(cast_range - 2 metres, 0). Returns (nil, 0, nil, 0) when picks is not a table or neither item is ready/picked. |
| `press_now` | `hx_close_in.press_now(ctx: table, step: table) -> any` | safe | Steps.press(ctx, step) then returns Steps.complete(ctx, step). Convenience for the common press-and-finish path. |
| `reach` | `hx_close_in.reach(dist: number, base: number, warp: Ability, warp_u: number, strike: Ability, strike_u: number, short_warp?: boolean) -> string\|nil` | safe | Picks how to close the gap. "in" when dist<=base. "warp" when warp is present (short_warp true or dist>=warp_u) and dist<warp_u+base. "strike" when strike is present and dist<strike_u. "both" when warp and strike are present and dist<warp_u+strike_u. nil otherwise. |

### hx_items

`table` · tier `safe` — Item id/token tables and resolvers for the local player's active-item slots (4-7), plus a step-condition evaluator. Load it with local Item = require("hx_items").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ITEM` | `.ITEM: table` | safe | Map of item name string to integer item id, snapshot of HeroCfg.enums().ITEM taken at load. |
| `TOKEN` | `.TOKEN: table` | safe | Map of integer item id (ITEM.X) to its ability token string, snapshot of HeroCfg.item_tokens() taken at load. |
| `condition_met` | `hx_items.condition_met(ctx: table, step: table, ability: Ability) -> boolean` | safe | Evaluates step.cfg.condition against ability. OFF_CD and any unknown value return ability:can_activate(). CHAIN requires step.cfg.chain_target to resolve to an owned ability whose true_cooldown > 0 AND ability:can_activate(). WHILE_MOD requires step.cfg.modifier_trigger (non-empty) to match on ctx.lp — or on U.pawn_of(step.target) or ctx.target when modifier_scope is ENEMY/STEP_TARGET — via :matches_predicates, AND ability:can_activate(). Returns false if any required field is missing. |
| `index_of_token` | `hx_items.index_of_token(token: string) -> integer\|nil` | safe | Reverse lookup from token string to its ITEM id. nil for a non-string, empty string, or token not in the TOKEN table. The reverse index is built once at module load. |
| `is_echo` | `hx_items.is_echo(item: integer) -> boolean` | safe | True iff item is ITEM.EchoShard or ITEM.Refresher. |
| `is_self_silencing` | `hx_items.is_self_silencing(item: integer) -> boolean` | safe | True iff the item's known definition is flagged self_silencing (currently only ITEM.EtherealShift). |
| `resolve` | `hx_items.resolve(lp: PlayerPawn, item: integer) -> Ability,integer\|nil` | safe | Resolves an ITEM id to lp's owned active-item ability and its active-slot index 0..3. Returns nil when lp is missing, item is nil or 0, the token is unknown, HERO_LIB.owned_item has no ability, or the ability's :get_slot() is not an integer in 4..7 (i.e. the item is not currently in an active slot). |
| `resolve_token` | `hx_items.resolve_token(lp: PlayerPawn, token: string) -> Ability,integer\|nil` | safe | Same as resolve but keyed by token string. Returns nil for a missing lp, non-string or empty token, no owned ability, or an ability whose slot is not 4..7; otherwise (Ability, slot-4). |
| `target_of` | `hx_items.target_of(item: integer) -> string` | safe | Returns the target style of the item: "self" (most actives), "self_dir" (dash-style WarpStone/ShadowStep/MagicCarpet/MajesticLeap), "ally" (RescueBeam/DivineBarrier/ShrinkRay), "ground" (ColdFront/AlchemicalFire/VortexWeb/GuardianWard/ArcticBlast/MysticalPiano). Anything not in the table — including unknown items — falls through to "enemy". |
| `token` | `hx_items.token(item: integer) -> string\|nil` | safe | Shorthand for TOKEN[item]: the item id's ability-token string, or nil if the id is not in the TOKEN table. |

### hx_items_first

`table` · tier `safe` — Fixed-order driver that casts owned active items in a canonical priority list; knows per-item 'kind' (self / ground / aura / tribute / weave / refresher / plain) and dispatches each one correctly. Load it with local IF = require("hx_items_first").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ORDER` | `.ORDER: table` | safe | Fixed array of 19 { token, kind } pairs defining the canonical cast order. kind is one of "refresher", "ground", "aura", "weave", "self", "plain", "tribute" and selects how run() casts each item. |
| `feet` | `hx_items_first.feet(ctx: table, ab: Ability, role: string, prio: integer, smooth?: number) -> boolean` | safe | Aims straight down at the player's feet with aim.type DEFAULT, pitch 89, and the given mouse smoothing (default 20) via HERO_LIB.aim on ctx.cmd. On aim-settled, leases (prio, role) and queues :item(ab); on process, clears the STEP-priority lease bit for the item. Returns true iff HERO_LIB.aim_status_consumes_combo on the status is true. Uses a shared module-local FEET/FEET_CALL table — do not call reentrantly. |
| `rows` | `hx_items_first.rows(pickers: table) -> table` | safe | Projects ORDER through pickers (a map of key -> list-of-tokens) into an array of { token, kind, key, idx } rows in ORDER's order. For each row, scans every list in pickers and sets key/idx to the first (key, position) whose token matches; both stay nil if no list contains it. Rebuilt on every call. |
| `run` | `hx_items_first.run(ctx: table, rows: table, in_cd: boolean, o: table) -> boolean` | safe | Walks rows and casts the picked ones. A row is picked by o.picked(row, o.block) or, by default, when o.block[row.key][row.idx] is true. Resolves the token to an ability; if it is already in cast-delay or channeling and o.busy_holds is true, counts as used; otherwise if HERO_LIB.is_ability_ready and (not in_cd or row.kind == "refresher"), dispatches by kind: refresher casts only while in_cd; ground calls o.ground(ctx,row,ab,o.role,o.prio) or falls back to feet(); aura skips unless ability's ActiveRadius has at least one ally in it; tribute skips while the blood-tribute modifier is live or within 2*interval+latency of ctx.hero.tribute_at (and records tribute_at); self alt_casts via lease; weave presses IN_ATTACK when the primary weapon has ammo and the player is not disarmed; plain just leases :item(ab). Returns true if any row ended up as a used cast or busy-hold. |
| `run_for` | `hx_items_first.run_for(ctx: table, rows: table, in_cd: boolean, o: table, block: table, role: string) -> boolean` | safe | Sets o.block and o.role to the supplied values for the duration of a single run() call and clears them afterwards; returns run()'s used result. Mutates o in place. |

### hx_feature_autocast

`table` · tier `safe` — Factories and helpers for the Auto Cast feature family (charge-and-release, instant, special-ult) plus enemy-metering and 'use before incoming threat' logic. Load it with local AC = require("hx_feature_autocast").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `VERDICT` | `.VERDICT: table` | safe | Verdict codes passed to report / HERO_LIB.special_ult_report: { WAITING=1, CAST=2, PREVENTED=3 }. |
| `WHEN` | `.WHEN: table` | safe | 'When to use' enum for feature configs: { MANUAL=1, SAFE=2, USE=3 }. |
| `WHEN_ROLE` | `.WHEN_ROLE: table` | safe | Maps a WHEN value to the action.decide role string: MANUAL -> "offense_assist", SAFE -> "defense", USE -> "offense_auto". |
| `helper_steps` | `hx_feature_autocast.helper_steps(cfg: table, H: table) -> table` | safe | Builds auto-slot helper step entries for slots 0..3. Skips when cfg.content.helpers or cfg.slot_opts.helper are not tables. Emits a step for each slot whose cfg.content.helpers[slot+1] is true, is not already a casting feature in H.features, and whose Cfg.helper_fires_when is TARGET_VISIBLE or COOLDOWN_READY. Each emitted entry is { kind="ability", slot, host_slot=slot, source="auto_slot", helper=true, cfg=nil, state={}, fires_when, slot_opts }. Returns the (possibly empty) array. |
| `make` | `hx_feature_autocast.make(o?: table) -> table` | safe | Builds a charge-and-release Auto Cast feature definition. o.slot (default 0), o.key, o.name, o.blurb, o.bind (default true) parameterise the feature. Exposes a Mode enum (Arm+fire / Fire only — in Fire-only mode on_tick returns early unless engaged and Chg.clock returns a positive clock) and a hold_upto slider (0.5..8 s, default 3). on_tick runs a persistent 'auto_cast' step via Steps.exec; when the step is HOLD/WAIT while engaged it tracks ctx.hero[hkey] and Steps.abandon("hold-expired") after hold_upto seconds. Not available during combo (runs_during_combo=false). |
| `make_instant` | `hx_feature_autocast.make_instant(o?: table) -> table` | safe | Builds an instant Auto Cast feature: no mode or hold, no state tracking beyond Steps. on_tick resets a persistent 'auto_cast' step and immediately Steps.exec's it, optionally gated by o.can_engage(ctx) when provided. runs_during_combo=false, casts=true. |
| `meter_pick` | `hx_feature_autocast.meter_pick(ctx: table, content: table, radius: number, q?: any) -> PlayerPawn\|nil,integer` | safe | Picks the best living enemy hero within radius of ctx.lp using HERO_LIB.get_heroes_in_radius(origin, radius, q). Meter mode comes from content.enemy_meter (default BY_HERO=0): BY_HERO with a non-empty content.priority_heroes list returns the first enemy whose hero id appears in that list (and nil if none match); LOWEST_HP=1 picks lowest absolute :get_health; LOWEST_HP_PCT=2 picks lowest hp/max; NEAREST=3 picks nearest by Distance. Returns (pawn, n) or (nil, 0); reuses a module-local scratch array. |
| `report` | `hx_feature_autocast.report(pick: PlayerPawn\|nil, verdict: integer, n: integer, radius: number)` | safe | Forwards to HERO_LIB.special_ult_report with pick:get_hero_id() (or -1 when pick is nil), the verdict code, enemy count n, and radius. |
| `special_ult` | `hx_feature_autocast.special_ult(o?: table) -> function` | safe | Returns an on_tick(ctx) closure for a special-ultimate feature. o.slot (default 3) picks the ability; o.escape enables low-hp firing. Each tick, bails unless ctx.cfg.content.special_ult_auto is true, resolves the ability, and (when AoE radius > 0) meter_picks a target. Fires when any of: hp% <= content.auto_safe_hp (escape only); content.use_before.death is set and HERO_LIB.damage_taken(lp, 1.0) >= current hp; use_before_due accepts the earliest cc/ult threat; or content.auto_use is true with a pick and not in combo. If content.prevent_fails is true and n < 1, flips the fire to PREVENTED instead. Dispatches via a persistent 'special_step' with step.target = pick (and role="defense" + direct_press=true for death/threat answers), reports verdict via report(), and on CAST moves ctx.hero.ub_threat to ctx.hero.ub_done. |
| `use_before_due` | `hx_feature_autocast.use_before_due(ctx: table, th: table, ab: Ability, slot: integer) -> boolean` | safe | Decides whether threat th should be answered this tick. Returns false if th.id == ctx.hero.ub_done or th.answered; true if th.id == ctx.hero.ub_threat (already answering); otherwise false unless th.eta_ms <= AbilityCastDelay*1000 + 20 ms, action.decide("defense", slot_act(slot)) == "act", and HERO_LIB.threat_answer(th.id, true) accepts — then sets ctx.hero.ub_threat = th.id and returns true. |
| `use_before_threat` | `hx_feature_autocast.use_before_threat(c: table) -> table\|nil` | safe | Returns the earliest incoming threat to pre-empt based on c.use_before: HERO_LIB.threat("cc") when crowd_control is true, HERO_LIB.threat("ult") when enemy_ult is true. If both are present returns the one with the lower eta_ms. nil when c.use_before is not a table or HERO_LIB.threat is unavailable. |

### hx_rook_flight

`table` · tier `safe` — Flight-path solver for the Rook ability: picks a landing point and verifies the current view would still land a hit. Load it with local Rook = require("hx_rook_flight").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `solution` | `hx_rook_flight.solution(ctx: table, ability: Ability, target: PlayerPawn) -> Vector3,table\|nil` | safe | Plans a Rook flight. Reads vdata.m_projectileInfo for speed (modified by ABILITY_PROJECTILE_SPEED_PERCENT and capped by sv_maxvelocity), capsule radius and axis-aligned trigger centres (requires x=y=0 on both), deploy gap, above-ground, fall rate, climb, step-down, trace radius, pitch limits, and remaining cast delay; nil if any field is missing or non-positive. Simulates the caster's movement over the remaining delay to compute a cast offset, then simulates target movement for up to 512 ticks (min 128) sampling pos + vel*latency. For each of three lanes (centre, +gap/2, -gap/2) iterates up to 4 refinements of cmd:predict_aim_camera + utils.calc_angle until the yaw settles within 0.01, then validates with a dual-marble first-leg sim (gravity-fall + climb-over-ledge + capsule-vs-target hit test with a golden-section search). Returns (landing-point Vector3, params table c) on the first lane that confirms a hit, or nil. Caches path samples and PATH {tick, index, count, mins, maxs} for view_hits. |
| `view_hits` | `hx_rook_flight.view_hits(ctx: table, target: PlayerPawn, silent?: boolean) -> boolean` | safe | Re-runs the first-leg hit sim against the path cached by the most recent solution() call. Returns false if PATH.tick ~= ctx.tick or PATH.index ~= target:get_index() (stale/wrong target), or if the required cmd fields are missing. silent=true samples cmd.viewangles; otherwise cmd.ang_camera_angles. Projects the camera forward 10000 units through predict_aim_camera, then returns whether rook_first_leg finds a capsule hit on either marble. |

### hx_feature_headlock

`table` · tier `safe` — Factory for Head-Lock features that aim a hitscan ability at the target's head (or auto-fire it) while it is live. Load it with local HL = require("hx_feature_headlock").

| Member | Signature | Tier | Description |
|---|---|---|---|
| `make` | `hx_feature_headlock.make(o?: table) -> table` | safe | Builds a Head-Lock feature. o.slot (default 0) selects the ability, o.auto_fire makes it fire automatically (sets casts=true, runs_during_combo=false; otherwise casts=false, runs_during_combo=true — i.e. steer-only runs during combo). o.is_live(ctx, ability) is required and gates every tick. Each tick: resolves the ability, loads the aim config via Aim.effective + Cfg.aim, picks a target via Tgt.pick, aims at the head via Tgt.force_head_aim — but falls back to Tgt.aim_point when Safety mode is active (safety.active() true). Stops if there is no target, target is the local player, or Tgt.can_cast rejects the pose. In auto-fire mode gates on action.decide("offense_auto") == "act" and dispatches via Steps.deliver. Otherwise forwards to Bus.request with psilent derived from aim.mode — HYBRID uses aim.allow_unsafe_psilent or Bus.reach_ok, other modes via Cfg.uses_psilent. |

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
| `ease_in_out_cubic` | `ease_in_out_cubic(t: number) -> number` | safe | Standard cubic ease-in-out curve on t; no input clamp. |
| `deadline` | `deadline(seconds: number) -> number` | safe | Returns the platform-time timestamp `seconds` from now (pair with `is_past`). |
| `target_selection` | `target_selection(target: any?, priority: integer?, source: integer?, confidence: number?, reason: string?) -> lua_target_selection_wrapper_t` | safe | Builds a target-selection wrapper from the optional positional fields; each argument is applied only when it matches the expected type. |
| `game_time` | `game_time() -> number` | safe | Current server game time in seconds (same source the combat layer uses). |
| `ease_in_out_quad` | `ease_in_out_quad(t: number) -> number` | safe | Quadratic ease-in/out of `t`: `2t^2` below 0.5, otherwise `-1 + (4 - 2t)·t`. Input is not clamped. |
| `ensure_shared` | `ensure_shared(name: string) -> table` | safe | Returns the existing global table at `name`; otherwise creates an empty table, stores it as that global, and returns it. |
| `hero_name_of` | `hero_name_of(id: integer) -> string` | safe | Returns the lowercase codename for the given `EHeroID_t` value; empty string when the id is unknown. |
| `ease_in_quad` | `ease_in_quad(t: number) -> number` | safe | Quadratic ease-in: returns `t*t`. |
| `is_key_down` | `is_key_down(vk: integer) -> boolean` | safe | Returns true if virtual-key `vk` is currently held in-game; returns false for codes outside 0-255. |
| `interval_per_tick` | `interval_per_tick() -> number` | safe | Returns the engine's tick interval in seconds; falls back to `1/64` when global vars are unavailable. |
| `ease_out_cubic` | `ease_out_cubic(t: number) -> number` | safe | Cubic ease-out curve: `(t-1)^3 + 1`. |
| `is_key_pressed` | `is_key_pressed(vk: integer) -> boolean` | safe | True on the frame the given virtual-key transitions down, suppressed while the user is typing. |
| `is_hero_id_valid` | `is_hero_id_valid(id: integer) -> boolean` | safe | True when `id` maps to a known hero codename in the hero-name table. |
| `ease_out_quad` | `ease_out_quad(t: number) -> number` | safe | Quadratic ease-out: t * (2 - t). |
| `is_key_released` | `is_key_released(vk: integer) -> boolean` | safe | True on the edge the given virtual key was released this frame, suppressed while the user is typing in a text field. |
| `Vec2` | `Vec2(x: number?, y: number?) -> Vec2` | safe | Constructs a Vec2; with no args or fewer than two args returns a zero Vec2, otherwise Vec2(x, y). |
| `raw_ptr` | `raw_ptr(addr: integer) -> lua_raw_ptr_t` | safe | Wraps a numeric address in a raw-pointer userdata; returns an invalid pointer if the first argument is not an integer address. |
| `CHandle` | `CHandle(raw: integer?) -> CHandle` | safe | Constructs a CHandle from a raw packed integer; returns an invalid handle when the argument is missing or non-integer. |
| `qangle` | `qangle(p: number, y: number, r: number) -> QAngle` | safe | Constructs a QAngle from pitch, yaw, roll. |
| `smoothstep` | `smoothstep(edge0: number, edge1: number, x: number) -> number` | safe | Hermite smoothstep: returns 0 when edge0 == edge1; otherwise clamps (x-edge0)/(edge1-edge0) to [0,1] and returns t*t*(3 - 2*t). |
| `is_past` | `is_past(target: number) -> boolean` | safe | Returns true when the current kusd-tick seconds reading is at or past target (as produced by deadline()). |
| `real_time` | `real_time() -> number` | safe | Returns CGlobalVarsBase::m_flRealTime, or 0 when the globals pointer is unavailable. |
| `Ray` | `Ray(start: Vector3\|nil, finish: Vector3\|nil, mins: Vector3\|nil, maxs: Vector3\|nil) -> Ray` | safe | Builds a Ray_t from up to four Vector3 arguments (Start, End, Mins, Maxs); any missing or non-Vector3 slot stays at the default. |
| `color_alpha` | `color_alpha(c: Color, a: integer) -> Color` | safe | Returns a copy of `c` with its alpha channel replaced by `a`. |
| `lerp` | `lerp(a: number, b: number, t: number) -> number` | safe | Linearly interpolates from `a` to `b` by `t` (not clamped). |
| `collectgarbage` | `collectgarbage(opt: string\|nil, ...: any) -> any` | safe | Sandboxed replacement for the stock `collectgarbage`; accepts the standard options (`collect`, `count`, `stop`, `restart`, `step`, `setpause`, `setstepmul`, `isrunning`, `generational`, `incremental`) and returns the matching Lua GC result. |
| `tick_count` | `tick_count() -> integer` | safe | Returns `CGlobalVarsBase::m_nTickCount`; 0 when global vars aren't resolved. |
| `color_from_hex` | `color_from_hex(hex: string) -> Color` | safe | Parses a `#RRGGBB` or `#RRGGBBAA` string (leading `#` optional); alpha defaults to 255 and strings shorter than 6 hex digits yield `Color()`. |
| `platform_time` | `platform_time() -> number` | safe | Monotonic platform time in seconds, read from `KUSER_SHARED_DATA` (not affected by game pause). |
| `to_screen` | `to_screen(worldPos: Vector3) -> table\|nil` | safe | Projects a world-space position to screen; returns `{x, y, visible = true}` or nil when the point is behind the camera or off-screen. |
| `lua_menu_handle_t` | `lua_menu_handle_t(path: string) -> lua_menu_handle_t` | safe | Builds a menu handle for the config path `path`, resolving the node's kind and FNV-1a token when the path exists; returns an empty handle if `path` is missing or does not resolve. |
| `color_hsv` | `color_hsv(h: number, s: number, v: number, a: number?) -> Color` | safe | Builds a Color from HSV components (h in degrees, s/v in 0..1); alpha defaults to 255. Any missing argument falls back to h=0, s=1, v=1. |
| `sign` | `sign(x: number) -> integer` | safe | Returns 1 for positive x, -1 for negative, 0 for zero. |
| `vec3` | `vec3(x: number, y: number, z: number) -> Vector3` | safe | Constructs a Vector3 from three components. |
| `color_lerp` | `color_lerp(a: Color, b: Color, t: number) -> Color` | safe | Linearly interpolates each channel from `a` to `b` by `t`. |
| `load` | `load(...: any) -> nil` | safe | Sandbox stub replacing the standard `load`: ignores its arguments and returns no values, so dynamic code loading is disabled. |
| `color_pack_argb` | `color_pack_argb(c: Color) -> integer` | safe | Packs the color's channels into a 32-bit ARGB integer. |
| `loadstring` | `loadstring(...: any) -> nil` | safe | Sandbox stub: always returns nothing. Dynamic code loading from Lua is disabled. |
| `convar_lookup` | `convar_lookup(name: string) -> any` | safe | Looks up a ConVar by name and returns its current value (through the convar table's lookup helper). |
| `color_pack_rgba` | `color_pack_rgba(c: Color) -> integer` | safe | Packs a Color into a 32-bit RGBA integer (red in the top byte, alpha in the low byte). |
| `Notification` | `Notification(arg: string\|table)` | safe | Shows a notification toast; when `arg` is a table reads `primary_text` / `secondary_text` (falling back to `id`, then the literal "Notification" for the title), otherwise logs the string through the Lua console as an info line. |
| `Vector3` | `Vector3(x: number, y: number, z: number) -> Vector3` | safe | Constructs a Vector3 from three numbers; returns a zero vector if fewer than three arguments are supplied. |
| `lua_target_selection_wrapper_t` | `lua_target_selection_wrapper_t(...: any) -> lua_target_selection_wrapper_t` | safe | Constructs a default-initialised target-selection wrapper; `TargetSelection` is set to this constructor when not already defined. |
| `color_scale` | `color_scale(c: Color, s: number) -> Color` | safe | Multiplies the RGB channels by s (clamped to byte range) and keeps the original alpha. |
| `approach` | `approach(cur: number, target: number, step: number) -> number` | safe | Moves cur toward target by at most abs(step) units and returns the new value; snaps to target when within one step. |
| `color_unpack_argb` | `color_unpack_argb(argb: integer) -> Color` | safe | Decodes a 32-bit ARGB-packed integer into a Color (A in the high byte). |
| `clamp` | `clamp(x: number, lo: number, hi: number) -> number` | safe | Clamps a float into [lo, hi]. |
| `distance_between` | `distance_between(a: Vector3, b: Vector3) -> number` | safe | Returns the 3D distance between two world points (Math::Distance3D). |
| `menu_handle` | `menu_handle(path: string) -> lua_menu_handle_t` | safe | Alias of `lua_menu_handle_t`; resolves a menu path to a handle (kind/token/desc filled when a matching node exists, otherwise just the path). |
| `Color` | `Color(...: any) -> Color` | safe | Constructs a Color: a single integer argument is unpacked as 0xRRGGBBAA, otherwise up to four values are taken as (r, g, b, a) with any missing channel defaulting to 255 and each argument coerced to a byte. |
| `draw_line_alpha_fade` | `draw_line_alpha_fade(a: Vector3, b: Vector3, color: Color, alpha: number)` | safe | No-op stub kept for script compatibility; the registered binding does nothing. |
| `clamp_int` | `clamp_int(x: integer, lo: integer, hi: integer) -> integer` | safe | Returns x clamped to [lo, hi]. |
| `distance_between_2d` | `distance_between_2d(a: Vector3, b: Vector3) -> number` | safe | Returns the 2D (XY-plane) distance between a and b (`Math::Distance2D`). |
| `ease_in_cubic` | `ease_in_cubic(t: number) -> number` | safe | Cubic ease-in: returns t*t*t. |
| `clear_shared` | `clear_shared(name: string)` | safe | Removes the named shared global by assigning nil to it. |
| `print` | `print(...: any) -> nil` | safe | Tab-joins its arguments via `tostring`, logs the line to the Lua console as info under the current script's name, and mirrors it to the dev log. |
| `frame_time` | `frame_time() -> number` | safe | Engine `m_flAbsoluteFrameTime` for the current frame; 0 when GlobalVars is unavailable. |
| `ImColor` | `ImColor(...: any) -> Color` | safe | Alias of `Color`; constructs a Color from (r,g,b[,a]) byte channels, or from a single packed 32-bit ARGB integer. Missing channels default to 255. |
| `TargetSelection` | `TargetSelection() -> lua_target_selection_wrapper_t` | safe | Alias of `lua_target_selection_wrapper_t`: returns a default-constructed target selection record. |
| `Vector` | `Vector(x: number, y: number, z: number) -> Vector3` | safe | Alias of `Vector3`. |

## Callbacks

Register a handler and the engine calls it on the matching event.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_createmove` | `on_createmove(cmd: UserCmd)` | safe | Fires on each outgoing user-command tick; receives the UserCmd about to be sent. |
| `on_pre_frame` | `on_pre_frame()` | safe | Fires once per client frame, before the engine runs its frame work. |
| `on_frame` | `on_frame()` | safe | Fires once per client frame. |
| `on_post_frame` | `on_post_frame()` | safe | Fires once per client frame, after the engine's frame work. |
| `on_pre_framestage` | `on_pre_framestage(stage: integer)` | safe | Fires before each client frame stage; receives the stage index (see `callback.FrameStage.FRAME_*`). |
| `on_post_framestage` | `on_post_framestage(stage: integer)` | safe | Fires after each client frame stage; receives the stage index (see `callback.FrameStage.FRAME_*`). |
| `on_map_load_start` | `on_map_load_start()` | safe | Map load begins (before pawn spawn). |
| `on_map_load_full` | `on_map_load_full()` | safe | Local pawn spawned into a live match. |
| `on_game_start` | `on_game_start()` | safe | The match went live (game state -> GameInProgress, 7). CHANGED: used to fire at WaitForMapToLoad. |
| `on_game_end` | `on_game_end(winner_team: integer)` | safe | The match ended (game state -> PostGame, 8); the winning team is passed. CHANGED: used to fire at PreGameWait. |
| `on_round_start` | `on_round_start()` | safe | The game rules' round start time changed. |
| `on_round_end` | `on_round_end(winner_team: integer)` | safe | Fires with on_game_end when a round was live. |
| `on_render` | `on_render()` | safe | Fires once per rendered frame, on the render thread. |
| `on_entity_created` | `on_entity_created(entity: Entity, idx: integer)` | safe | Fires when an entity enters the world; receives (entity, index). |
| `on_entity_deleted` | `on_entity_deleted(entity: Entity\|nil, idx: integer)` | safe | Fires when an entity leaves the world; receives (entity, index). |
| `on_modifier_added` | `on_modifier_added(mod: lightuserdata, holder_handle: lightuserdata, modifier: Modifier\|nil, target: PlayerPawn\|Entity\|nil, caster: PlayerPawn\|Entity\|nil)` | safe | Game thread. A modifier (buff/debuff) was added to an entity. Handlers get (mod, holder_handle, modifier, target, caster): mod is the modifier and holder_handle the holder's entity handle, both light userdata (as before); modifier is the Modifier usertype; target is the entity holding it and caster the modifier's caster (PlayerPawn for a hero pawn, else Entity; nil when gone). The last three are nil off the game thread. CHANGED: the last three arguments are new; earlier docs called the first two (Modifier, PlayerPawn), which they never were. Alias of on_add_modifier. |
| `on_modifier_removed` | `on_modifier_removed(mod: lightuserdata, holder_handle: lightuserdata, modifier_name: string\|nil, target: PlayerPawn\|Entity\|nil, caster: PlayerPawn\|Entity\|nil)` | safe | Game thread. Fires just BEFORE the engine frees a modifier: read it now, do NOT retain the pointer. Handlers get (mod, holder_handle, modifier_name, target, caster): mod and holder_handle are light userdata as before; modifier_name is the modifier's name (the modifier is freed right after the event); target / caster as on_add_modifier. CHANGED: the last three arguments are new. Alias of on_remove_modifier. |
| `on_fire_bullets` | `on_fire_bullets(ctx: any)` | safe | Game thread. Defined by a script: called with an opaque bullet context. Called as on_fire_bullets(fn): registers fn on bullet_create, exactly like on_bullet_create. |
| `on_take_damage` | `on_take_damage(ev: any, name: string)` | safe | Fires when a pawn takes damage; receives a table with `attacker`, `victim`, `hitgroup`, `damage` and `ability_id`. |
| `on_particle_create` | `on_particle_create(ctx: any)` | safe | Fires when a particle system is created; receives a table with `particle_index`, `name`/`path`, attach info, `is_local` and `position`. |
| `on_game_event` | `on_game_event(ev: GameEvent, name: string)` | safe | Fires on a client game event; receives (event, name). |
| `on_user_message` | `on_user_message(id: integer, bytes: string) -> boolean` | safe | Fires on an incoming user message; receives (msg_id, bytes); return true to swallow the message. |
| `on_net_message` | `on_net_message(id: integer, bytes: string) -> boolean` | safe | Fires on an incoming net message; receives (msg_id, bytes); return true to swallow the message. |
| `on_draw` | `on_draw()` | safe | Primary render callback — fires every frame on the RENDER thread. Do 2D/3D drawing (Render / ImGui / Aim world-to-screen) here, not game-thread entity reads. |
| `on_preview_draw` | `on_preview_draw(plate: table)` | safe | Shorthand for Preview.on_draw. Fires every frame the in-menu ESP preview plate is visible (Visuals tab, Enemies or Allies section, or Entities takeover). plate is the stage rect in screen pixels. Use the regular draw.* primitives with plate.x + offset coordinates; they are retargeted to the plate's drawlist and clipped to the stage. |
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
| `on_typing_start` | `on_typing_start(fn: function, opts: table?) -> integer` | safe | Global shim that adds `fn` as a handler on the `typing_start` channel; returns the handler id (0 if `fn` is not a function). |
| `on_console_output` | `on_console_output(fn: function, opts: table\|nil) -> integer` | safe | Registers a handler on the `console_output` channel, which fires for each game console line; returns the handler id (0 on bad input). |
| `on_unload` | `on_unload(fn: function, opts: table\|nil) -> integer` | safe | Registers a handler on the `unload` channel, which fires when the owning script is unloaded; returns the handler id (0 on bad input). |
| `on_cursor_hidden` | `on_cursor_hidden(handler: function) -> any` | safe | Shorthand global that attaches `handler` to the `cursor_hidden` channel, equivalent to `callback.on_cursor_hidden:add(handler)`. |
| `on_cursor_shown` | `on_cursor_shown(fn: any, opts: table?) -> integer` | safe | Registers a handler on the `cursor_shown` channel and returns its handler id (0 if `fn` isn't a function). |
| `on_input` | `on_input(handler: function, opts: table?) -> integer` | safe | Shorthand that registers a handler on the input channel; input events fire with the current frame's input payload. Returns the handler id, or 0 if the first argument is not a function. |
| `on_input_key_down` | `on_input_key_down(vk: integer, down: boolean)` | safe | Subscribes to the input_key_down channel; the handler is invoked when a key goes down with the virtual-key code and down=true. |
| `on_input_key_up` | `on_input_key_up(handler: fun(...):any) -> integer` | safe | Registers a handler on the `input_key_up` channel (keyboard/mouse release events) and returns its id. |
| `on_connect` | `on_connect(handler: fun(map_name:string):any) -> integer` | safe | Fires once the local client is in a match (map load or state transition into InMatch); `map_name` is the loaded map. |
| `on_load` | `on_load(handler: fun(...:any)) -> integer` | safe | Adds `handler` to the `load` channel; returns the handler id. |
| `on_disconnect` | `on_disconnect(handler: fun(...:any)) -> integer` | safe | Adds `handler` to the `disconnect` channel; returns the handler id. |
| `on_menu_close` | `on_menu_close(fn: function, opts: table?) -> integer` | safe | Shorthand setter: adds the function as a handler on the "menu_close" channel (fires when the overlay menu closes) and returns the handler id, or 0 if arg 1 is not a function. |
| `on_hero_killed` | `on_hero_killed(fn: function, opts: table?) -> integer` | safe | Global setter that adds a handler to the "hero_killed" channel (fires when a hero dies) and returns the handler id. |
| `on_menu_open` | `on_menu_open(fn: fun()) -> integer` | safe | Handler channel fired when the Avalanche menu becomes open; the global form adds `fn` to the `menu_open` channel and returns the row id. |
| `on_local_pawn_change` | `on_local_pawn_change(fn: fun(...)) -> integer` | safe | Setter global: subscribes `fn` to the `local_pawn_change` channel and returns the row id; fires whenever the resolved local pawn changes. |
| `on_post_render` | `on_post_render(fn: function, opts: table?) -> integer` | safe | Subscribes a handler on the `post_render` channel and returns the handler id, or 0 if fn is not a function. |
| `on_local_pawn_death` | `on_local_pawn_death(fn: function, opts: table?) -> integer` | safe | Subscribes a handler on the `local_pawn_death` channel; fired when the local pawn dies. Returns the handler id. |
| `on_pre_render` | `on_pre_render(fn: fun(...)) -> integer` | safe | Global setter that registers `fn` as a handler on the `pre_render` channel (fires once per frame before rendering); returns the handler id or 0 if `fn` is not a function. |
| `on_local_pawn_spawn` | `on_local_pawn_spawn(fn: fun(...)) -> integer` | safe | Global setter that registers `fn` as a handler on the `local_pawn_spawn` channel (fires when the local pawn spawns); returns the handler id or 0 if `fn` is not a function. |
| `on_present` | `on_present(fn: function, opts: table?) -> integer` | safe | Attaches fn as a handler on the `present` channel (one per D3D Present); returns the handler id, or 0 if fn is not a function. |
| `on_map_change` | `on_map_change(fn: function, opts: table?) -> integer` | safe | Attaches fn as a handler on the `map_change` channel; returns the handler id, or 0 if fn is not a function. |
| `on_reload` | `on_reload(fn: function, opts?: table) -> integer` | safe | Subscribes fn to the "reload" channel (fires when scripts reload); returns the handler id, or 0 if arg 1 is not a function. |
| `on_scroll` | `on_scroll(delta: integer, horizontal: boolean)` | safe | Fires on each mouse-wheel event with the signed wheel delta and whether the scroll was horizontal; returning true from a handler claims the scroll. |
| `on_typing_end` | `on_typing_end(fn: function) -> CallbackHandle` | safe | Channel that fires when text input focus ends (user stops typing in an input field); the handle registers a listener on the `typing_end` channel. |

## Global constants

Enum ordinals + shared constant tables exposed at the top level.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Vector` | `.Vector: Vector3` | safe | Alias of Vector3 (LuaEntityAPI.cpp:186). |
| `ImColor` | `.ImColor: Color` | safe | Alias of Color. ImColor() with no arguments is opaque white. |
| `TargetSelection` | `.TargetSelection: lua_target_selection_wrapper_t` | safe | Factory alias of lua_target_selection_wrapper_t (LuaUsertypes.cpp:1981). |

---

_Generated from `src/data/lua_api.json` + `src/data/lua_bundled.json`. Regenerate with `npm run gen-lua-api`._
