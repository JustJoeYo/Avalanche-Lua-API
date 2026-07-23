# Avalanche Lua API

Flat, exhaustive reference of the **entire** Avalanche Lua scripting API.

> **Auto-generated — do not edit.** Derived from the in-game registry (`Avalanche LuaApiRegistry`, schema v1) via `npm run gen-lua-api`. For the full interactive docs (with prose walkthroughs, worked example scripts, and search) see **https://avalan.cc/developers/lua**.

**94** scopes · **1247** members · **16** globals · **36** callbacks · **3** aliases

**Trust tiers:** `safe` (available to every script, default) · `native` (low-level / powerful — enable explicitly) · `trusted` (restricted).

## Contents

- [Scopes](#scopes)
  - [Vector3](#vector3)
  - [Vec2](#vec2)
  - [Angle](#angle)
  - [Color](#color)
  - [Ability](#ability)
  - [PlayerPawn](#playerpawn)
  - [Entity](#entity)
  - [Modifier](#modifier)
  - [UserCmd](#usercmd)
  - [CUserCmd](#cusercmd)
  - [CallbackHandle](#callbackhandle)
  - [AddedCallbackHandle](#addedcallbackhandle)
  - [MenuNode](#menunode)
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
  - [Backtrack](#backtrack)
  - [log](#log)
  - [lua_convar_t](#lua_convar_t)
  - [lua_target_selection_wrapper_t](#lua_target_selection_wrapper_t)
  - [Particle](#particle)
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
  - [convar](#convar)
  - [global_ctx](#global_ctx)
  - [JSON](#json)
  - [Math](#math)
  - [Game](#game)
  - [Combat](#combat)
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
- [Compatibility aliases](#compatibility-aliases)

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
| `dist` | `:dist(other: Vector3) -> number` | safe |  |
| `dist_2d` | `:dist_2d(other: Vector3) -> number` | safe |  |
| `dot` | `:dot(other: Vector3) -> number` | safe |  |
| `cross` | `:cross(other: Vector3) -> Vector3` | safe |  |
| `normalized` | `:normalized() -> Vector3` | safe |  |
| `lerp` | `:lerp(other: Vector3, t: number) -> Vector3` | safe |  |
| `dir_to` | `:dir_to(other: Vector3) -> Vector3` | safe |  |
| `to_angles` | `:to_angles() -> table` | safe | Direction vector -> { pitch, yaw, roll }. |

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

`usertype` · tier `safe` — Citadel ability handle (upgrade-aware, identity-revalidated).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe |  |
| `get_name` | `:get_name() -> string` | safe |  |
| `get_class_name` | `:get_class_name() -> string` | safe |  |
| `get_scaled_property` | `:get_scaled_property(key: string) -> number` | safe |  |
| `list_properties` | `:list_properties() -> table` | safe | Enumerate every authored VData property as { PropertyName = scaledValue } (force-populated, upgrade-aware). Use it to discover a property's EXACT field name. |
| `get_property` | `:get_property(name: string) -> number` | safe |  |
| `get_cast_range` | `:get_cast_range() -> number` | safe |  |
| `get_aoe_radius` | `:get_aoe_radius() -> number` | safe |  |
| `get_slot` | `:get_slot() -> integer` | safe |  |
| `get_level` | `:get_level() -> integer` | safe |  |
| `get_target` | `:get_target() -> PlayerPawn\|nil` | safe |  |
| `get_upgrades` | `:get_upgrades() -> table\|nil` | safe |  |
| `get_upgrade` | `:get_upgrade(level: integer) -> boolean` | safe |  |
| `find_entities_in_cone` | `:find_entities_in_cone(range: number, angle_deg: number) -> PlayerPawn[]` | safe |  |
| `get_imbued_abilities` | `:get_imbued_abilities() -> table` | safe |  |
| `has_imbue_for` | `:has_imbue_for(...: any) -> boolean` | safe |  |
| `get_raw_vdata` | `:get_raw_vdata() -> raw_struct\|nil` | safe |  |
| `get_raw_struct` | `:get_raw_struct() -> raw_struct\|nil` | safe |  |
| `get_vdata` | `:get_vdata() -> table\|nil` | safe |  |
| `is_on_cooldown` | `:is_on_cooldown() -> boolean` | safe |  |
| `cooldown` | `:cooldown() -> number` | safe |  |
| `charges` | `:charges() -> integer` | safe |  |
| `can_be_executed` | `:can_be_executed() -> integer` | safe |  |
| `can_activate` | `:can_activate() -> boolean` | safe | Authoritative "can I press this ability/item button right now?" (cooldown/charges/cast-delay + stun/silence/mute gates). |
| `true_cooldown` | `:true_cooldown() -> number` | safe | Seconds until genuinely usable again: 0 = now, >0 = time to the NEXT USABLE CHARGE (per-charge recharge, not the full cooldown). |
| `is_refresh_item` | `:is_refresh_item() -> boolean` | safe | True iff this is a cooldown-reset ITEM: Echo Shard (PowerShard) or Refresher. Matched on the stable class-binding + designer token. |
| `has_refresh_target` | `:has_refresh_target() -> boolean` | safe | For a cooldown-reset item, whether the game would currently ACCEPT the cast (something IS refreshable) — i.e. NOT the "nothing to refresh" rejection that can_activate folds in. Refresher scans the whole signature kit; Echo Shard scans ONLY its own imbued abilities. False for a non-refresh item. |
| `can_place_on` | `:can_place_on(entity: PlayerPawn) -> boolean` | safe | Targeting validity: can this ability/item be placed on THIS candidate entity right now? Per-target companion of can_activate (which is target-independent). Replicates the game's per-candidate cast-validity from the ability's own vdata — location + team/type (ally/enemy/self) + range + cone + LOS — uniform for any ability/item on any hero. READ-ONLY query. |
| `has_alt_cast` | `:has_alt_cast() -> boolean` | safe | Does the ability support a SELF/ALT cast? True when its VData authors an alt-cast button token (the game's own marker for a self/no-target variant). Introspection for the engine's self-cast forcing: a step with TargetMode=Self presses IN_ALT_CAST so the cast lands on the local player regardless of the player's Quick/Confirm/Self cast setting. |
| `targeting_location` | `:targeting_location() -> integer` | safe | Raw targeting location (CITADEL_ABILITY_TARGETING_LOCATION / m_eAbilityTargetingLocation): 0 NONE (skillshot) · 1 SELF · 2 UNIT · 3 GROUND · 4 UNIT_OR_GROUND · 5 FIXED_RANGE_GROUND · 6 MINIMAP_GROUND · 7 MINIMAP_UNIT · 8 CUSTOM · 9 DEPLOYED_OBJECT. -1 if dead/unreachable. Static targeting metadata read off the live VData. The combo engine routes casts on this — can_place_on is meaningful ONLY for the UNIT kinds. |
| `is_unit_targeted` | `:is_unit_targeted() -> boolean` | safe | Is this an auto-aim, UNIT-targeted ability — targeting_location in {UNIT, UNIT_OR_GROUND, MINIMAP_UNIT}? True iff ability:can_place_on is the authoritative per-target validity gate for it. False for a skillshot (NONE), a ground/point cast, a self cast, or an unreachable VData — exactly the cases where can_place_on is meaningless and must NOT gate the cast. |
| `target_types` | `:target_types() -> integer` | safe | Raw CITADEL_UNIT_TARGET_TYPE bitfield (m_nAbilityTargetTypes) — which unit relationships the ability/item MAY target. Key bits: HERO_FRIENDLY 0x1 (allies, INCLUDES the caster/self), HERO_ENEMY 0x100. 0 if dead/unreachable. Static metadata off the live VData (the field SelfCastCatalog reads). With targeting_location/is_unit_targeted it classifies self-cast vs skillshot (loc==NONE: no enemy bit => self, enemy bit => skillshot) and the ally-vs-enemy side of a unit-attach item. |
| `__index` | `:__index(key: string) -> any` | native | Dynamic fallback after named methods: an m_*-prefixed key reads the live schema field off the ability's runtime class (m_flCastDelayStartTime/m_bChanneling/m_bHitAPlayer special-cased). Unknown -> nil (e.g. ability.m_flCooldownEnd). |

### PlayerPawn

`usertype` · tier `safe` — Citadel player pawn (hero entity).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe |  |
| `is_alive` | `:is_alive() -> boolean` | safe |  |
| `get_origin` | `:get_origin() -> Vector3` | safe |  |
| `get_velocity` | `:get_velocity() -> Vector3` | safe |  |
| `get_name` | `:get_name() -> string` | safe |  |
| `get_handle` | `:get_handle() -> integer\|nil` | safe | Full raw CHandle value (entry index + SERIAL bits); nil when the pawn is not live. Identical in meaning to Entity:get_handle(). Use this as a cache key when you need ENTITY IDENTITY: because it carries the serial, a recycled entry slot produces a DIFFERENT key (a cache miss) instead of silently hitting the dead occupant's entry. CHANGED: this previously returned the bare entry index (no serial) and 0 when not live -- so `if not h` never fired (0 is truthy in Lua) and recycled slots caused wrong cache hits. If you want the bare slot, use get_index(). |
| `get_index` | `:get_index() -> integer` | safe | Entity ENTRY index (bare slot, NO serial bits). The right key for a cache that means "this slot" and does not need entity identity; for an identity-stable key use get_handle(). Unchanged. |
| `get_vdata_class_name` | `:get_vdata_class_name() -> string` | safe |  |
| `get_health` | `:get_health() -> number` | safe |  |
| `get_max_health` | `:get_max_health() -> number` | safe |  |
| `get_scaling_stat` | `:get_scaling_stat(stat_type: integer) -> number` | safe |  |
| `get_starting_stat` | `:get_starting_stat(stat_type: integer) -> number` | safe |  |
| `get_modifier_value` | `:get_modifier_value(mod_type: integer, default_value?: number) -> number` | safe |  |
| `get_sum_modifier_value` | `:get_sum_modifier_value(mod_type: integer, default_value?: number) -> number` | safe |  |
| `can_be_lasthitted` | `:can_be_lasthitted(...: any) -> boolean` | safe |  |
| `get_team` | `:get_team() -> integer` | safe |  |
| `get_class_name` | `:get_class_name() -> string` | safe |  |
| `get_tech_resist` | `:get_tech_resist() -> number` | safe |  |
| `get_bullet_resist` | `:get_bullet_resist() -> number` | safe |  |
| `get_bone_pos` | `:get_bone_pos(bone_name: string) -> Vector3\|nil` | safe |  |
| `get_animgraph_symbols` | `:get_animgraph_symbols() -> string[]\|nil` | safe | PRIMARY light-vs-heavy melee tell: the broadcast animgraph SYMBOL strings (networked CGlobalSymbol array). The melee action/state string appears here — melee_charging (HEAVY windup, earliest), melee_heavy (heavy swing), melee_light1/melee_light2 (LIGHT), melee_ground_dashing/melee_air_dashing. index<->slot preserved ("" for a null slot); nil if not live/ready. Game-thread only. Read-only. |
| `get_animgraph_params` | `:get_animgraph_params() -> table\|nil` | safe | Full DUMP of every enemy-readable animgraph array plus chain diagnostics: { bools:boolean[], bytes:integer[], uint16s:integer[], ints:integer[], uints:integer[], uint64s:integer[], floats:number[], vectors:Vector3[], symbols:string[], bool_count_netvar:integer, poseRecipeSize:integer, sequence:integer, playbackRate:number, seqStart:number, dbg_str:string } or nil. FULLY schema-driven: every field offset comes from the live CSchemaSystem, RE fallback only if the schema returns 0. bools are bit-packed at the source. poseRecipeSize/playbackRate non-zero on an animating pawn confirm the chain reached CBaseAnimGraphController; dbg_str lists each field's resolved offset + whether it came from schema or fallback (fallback = unverified). Game-thread only. Read-only. |
| `get_animgraph_param` | `:get_animgraph_param(kind: string, index: integer) -> boolean\|integer\|number\|Vector3\|string\|nil` | safe | One scalar from the animgraph arrays. kind is one of "bool"\|"byte"\|"uint16"\|"int"\|"uint"\|"uint64"\|"float"\|"vector"\|"symbol"; index is 1-based. nil if out of range / not ready. |
| `get_animgraph_states` | `:get_animgraph_states() -> {vtable_off:integer, active:integer, count:integer, transitioning:boolean, id:integer}[]\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): enumerates every CNmStateMachineNode reached via a BOUNDED, SEH-guarded, canonical-pointer-gated scan from the pawn's CAnimationGraphInstance (chain: body+m_CBodyComponent -> ctrl+m_animationController -> +m_pAnimGraphInstance). vtable_off is the matched CNmStateMachineNode vtable's module-relative RVA (client.dll 0x27E2CF0 or animationsystem.dll 0x64A880) confirming identification; active is the +0x628 int16 active-state index (-1=invalid) — the candidate light-vs-heavy melee discriminator under test; count is the +0x28 declared state count (bounds for active); transitioning is +0x620!=0 (mid-blend); id is the node's raw heap address low-32 bits for cross-tick tracking. Nodes are returned in stable ascending-address order, capped at 32. Game-thread only, one-shot (not a hot path). Read-only. |
| `get_animgraph_dbg` | `:get_animgraph_dbg() -> string` | safe | DIAGNOSTIC companion to get_animgraph_states: runs the SAME body->ctrl->agi chain walk but ALWAYS returns the accumulated debug string (never nil) — resolved bodyOff/ctrlOff/agiOff with /schema or /fallback tags, the model-loaded precondition result, the ctrl address, and the RAW pointer value read at ctrl+agiOff printed as 0x%016llX (even when implausible, unlike get_animgraph_states which just says nil). Use this to see exactly where/why the states walk bails. Never wired into any feature. Game-thread only. Read-only. |
| `get_animgraph_dump` | `:get_animgraph_dump() -> table\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): dumps the AG2 pose-recipe blob and a handful of netvars counts using HARDCODED CLIENT-SCOPE offsets (NOT GetSchemaOffset() — this specific chain has been observed to resolve to a mixed client/server scope). Returns { recipeSize:integer, recipeVecCount:integer, recipe:string, symCnt_vec:integer, symCnt_field:integer, syms:string[], boolCnt_vec:integer, floatCnt_vec:integer, intCnt_vec:integer } or nil. recipeSize is m_nSerializePoseRecipeSizeAG2 (ctrl+0x1888); recipeVecCount is the recipe blob's own CUtlVector count (ctrl+0x1870); recipe is lowercase hex of the first up to 64 raw blob bytes (for eyeballing light-vs-heavy diffs — see the recipe-format RE notes for the byte layout); symCnt_vec/boolCnt_vec/floatCnt_vec/intCnt_vec are each array's own declared count (netvars+0xE0/0x08/0x98/0x50); symCnt_field is whichever of the four adjoining netvars+0x1E8/0x1EC/0x1F0/0x1F4 scalars numerically matches symCnt_vec (-1 if none do — only the 0x1E8 slot, m_nBoolVariablesCount, is schema-confirmed); syms is up to 16 SafeCStr-decoded symbol strings. Game-thread only. Read-only. |
| `get_graph_params` | `:get_graph_params() -> table\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): hunts for the CCitadelPlayerPawn_GraphController2 object (analog of CS2's CCSPlayerAnimationState) and scans it for CAnimGraph2ParamRefBase<T> blocks bound to known animgraph params — hero_action_is_instant (melee light/heavy discriminator candidate, instant=LIGHT), hero_action, base_state, hero_state, base_action, hero_action_is_alt_cast, movement_type, flinch. Tries base="ctrl" (CBaseAnimGraphController, body+0x4D0) first, then a bounded qword-value scan of pawn/body/ctrl for an EMBEDDED object whose own vtable ptr equals the resolved GraphController2 vtable (client.dll base + RVA 0x235e358) — candidates labeled "graphctrl2@<region>+0x<off>". Each candidate is then scanned 0x00..0x600 for ParamRef blocks (qword name-ptr matching a known param name). Returns { base:string, found:{ {name:string, cand:string, off:integer, idx:integer, bound:boolean, hex:string}[] }, tried:{ {base:string, hits:integer}[] } } or nil. found[].hex is the block's raw 0x20 bytes (wider than the documented 0x18-byte ParamRef) as lowercase hex, so a cached VALUE past the documented fields is visible without a second RE pass. Does NOT resolve a live value via idx — that needs a separate unresolved chain into the owning CAnimationGraphInstance. Game-thread only, one-shot (not a hot path). Read-only. |
| `get_instant_cast` | `:get_instant_cast() -> {pctrl:integer, vtbl_ok:boolean, bound:boolean, idx:integer, gi_nonnull:boolean, value:integer}\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): reads the m_InstantCast animgraph param LIVE VALUE (<-> "hero_action_is_instant", TRUE=instant/LIGHT melee, FALSE=charged/HEAVY) via a NEWLY-RE'd chain that SUPERSEDES the pawn+0x30->+0x4D0 CBaseAnimGraphController path used by every other animgraph reader here (that path reaches the WRONG similarly-named class for this field). Chain: pawn+0x830 DEREF -> pCtrl (the CCitadelPlayerPawn_GraphController2 instance) -> pCtrl+0x1F8 = m_InstantCast ParamRef record (CGlobalSymbol@+0, cached graph-instance ptr@+8, int16 m_nParamIndex@+0x10, bool m_bBound@+0x13) -> if bound: graphInstance=*(record+8) -> descArray=*(graphInstance+0x10) -> pDesc=descArray[idx] -> vcall pDesc's vtable slot 9 (offset +72, resolved directly off pDesc) with (pDesc, graphInstance+0x40, &out) writing the bool into out. Returns pctrl (low32 of pCtrl, 0 if null), vtbl_ok (pCtrl's vtable == client.dll+0x235E348, sanity-only), bound/idx/gi_nonnull (raw ParamRef record fields), and value (0/1 if the vcall succeeded, -1 if not bound / gi null / vcall guarded-faulted). Returns a table (not nil) even when pCtrl is null or the param is unbound — nil is reserved for a hard fault. Game-thread only, one-shot. Read-only. |
| `get_melee_state` | `:get_melee_state() -> {size:integer, vec_count:integer, dumped:integer, raw_hex:string, hash:integer, state:string, is_heavy:boolean, is_light:boolean}\|nil` | safe | DIAGNOSTIC ONLY (NOT wired into any feature): RAW hex dump of the AG2 pose-recipe byte blob (ctrl+0x1870/+0x1888, same chain as get_animgraph_dump), exactly the first `size` bytes. `hash` is the full little-endian uint32 at blob offset 4; `state` classifies bytes[5,6,7] of it into ready/windup/heavy_charge/heavy_hit/light_strike/light_settled/unknown, cross-checked 2026-07-22 on a REAL enemy-initiated melee edge (both light and heavy, not a mimic idle-poll). Fast not-heavy trigger: state=="light_strike" fires ~9 frames after the melee edge; state=="heavy_charge" (a sustained plateau from ~frame 13) is the suppress signal. See reference_animgraph_melee_state_read.md for the full byte-family table, the local+enemy cross-check data, and the timing comparison against the particle classifier. Game-thread only, one-shot. Read-only. |
| `get_trace` | `:get_trace(...: any) -> Vector3\|nil` | safe |  |
| `get_attachment` | `:get_attachment(name: string) -> Vector3\|nil` | safe |  |
| `visible` | `:visible() -> boolean` | safe |  |
| `is_visible` | `:is_visible() -> boolean` | safe |  |
| `has_modifier_state` | `:has_modifier_state(state: integer) -> boolean` | safe |  |
| `has_modifier` | `:has_modifier(name: string) -> boolean` | safe |  |
| `matches_predicates` | `:matches_predicates(csv: string) -> boolean` | safe | Any slug in the shared pred:/group:/state:/mod:/flag: vocabulary matches this entity. |
| `has_particle` | `:has_particle(path: string) -> boolean` | safe |  |
| `has_any_particle` | `:has_any_particle(...: string\|string[]) -> boolean` | safe | Any substring matches a particle recently created on this pawn. Accepts EITHER varargs strings `has_any_particle("a","b")` OR an array table `has_any_particle({"a","b"})` — both shapes work on every has_any_particle binding. No args => any recent particle at all. For anything TIMING-sensitive use get_particle_age instead: this stays true for the tracker's full 3s TTL. |
| `get_particle_age` | `:get_particle_age(...: string\|string[]) -> number\|nil` | safe | Seconds since the FRESHEST matching particle was created on this pawn, or nil if none is within the tracker's ~3s TTL. No args => age of the most recent particle of any path. Use this over has_any_particle whenever the question is a timing one (e.g. 'is this windup still live?'), since the boolean cannot distinguish a charge starting now from one that finished 3 seconds ago. |
| `get_abilities` | `:get_abilities() -> Ability[]` | safe |  |
| `get_ability` | `:get_ability(name: string) -> Ability\|nil` | safe | Resolve an ability by class name (FUZZY substring match — e.g. "citadel_ability_melee" also matches CCitadel_Ability_MeleeParry). |
| `get_ability_exact` | `:get_ability_exact(class: string) -> Ability\|nil` | safe | Resolve an ability by EXACT binding-class name (byte-for-byte), avoiding get_ability's fuzzy substring match. |
| `get_ability_by_slot` | `:get_ability_by_slot(slot: integer) -> Ability\|nil` | safe |  |
| `get_bone_position` | `:get_bone_position(bone_name: string) -> Vector3` | safe |  |
| `get_modifiers` | `:get_modifiers() -> Modifier[]` | safe |  |
| `get_modifier` | `:get_modifier(name: string) -> Modifier\|nil` | safe |  |
| `is_dormant` | `:is_dormant() -> boolean` | safe |  |
| `get_address` | `:get_address() -> integer` | safe |  |
| `get_angles` | `:get_angles() -> Vector3` | safe |  |
| `get_primary_weapon` | `:get_primary_weapon() -> Ability\|nil` | safe |  |
| `get_currency` | `:get_currency(...: any) -> integer` | safe |  |
| `get_account_id` | `:get_account_id() -> integer` | safe |  |
| `get_vdata` | `:get_vdata() -> raw_struct\|nil` | safe |  |
| `get_bones` | `:get_bones() -> table` | safe |  |
| `get_skeleton_instance` | `:get_skeleton_instance() -> integer` | safe |  |
| `get_min_fov_to_bones` | `:get_min_fov_to_bones(cam: Vector3, yaw_only?: boolean) -> number` | safe |  |
| `get_fireport_position` | `:get_fireport_position() -> Vector3` | safe |  |
| `get_model_name` | `:get_model_name() -> string` | safe |  |
| `get_particles` | `:get_particles() -> string[]` | safe | DISTINCT particle paths recently created on this pawn (within the tracker's ~3s TTL), oldest first. A path that re-spawns is refreshed in place rather than duplicated, so this lists what is recently live — not a spawn log. Empty if none / not live. |
| `get_particle_position` | `:get_particle_position(...: any) -> Vector3\|nil` | safe |  |
| `get_hitboxes` | `:get_hitboxes() -> table[]` | safe | Per-hitbox list: { center, bone_pos, mins, maxs, radius, capsule_a, capsule_b, capsule_radius, bone_index, shape } (no name field). |
| `get_bbox` | `:get_bbox() -> table\|nil` | safe | Axis-aligned bounding box { mins, maxs } (plus world / screen sub-tables). |
| `get_bounding_box` | `:get_bounding_box() -> table\|nil` | safe | Native screen-space bounding rect { x, y, w, h } (C_BaseModelEntity::GetBoundingBox) - NOT the same as get_bbox. |
| `closest_hitbox_point_to_ray` | `:closest_hitbox_point_to_ray(origin: Vector3, dir: Vector3) -> table\|nil` | safe | Closest hitbox-surface point to a ray. |
| `set_glow` | `:set_glow(color: Color, mode?: number, width?: number) -> boolean` | safe | Enable entity glow (see GlowMode). |
| `clear_glow` | `:clear_glow() -> boolean` | safe | Disable entity glow. |
| `get_player_name` | `:get_player_name() -> string` | safe | Display name of the controlling player (owning controller GetPlayerName); "" if no controller owns this pawn (e.g. a target dummy) or not live. |
| `get_controller` | `:get_controller() -> Entity\|nil` | safe | This pawn's owning CCitadelPlayerController as a generic Entity (read any controller schema field / :get_raw_struct); nil if none or not live. |
| `__index` | `:__index(key: string) -> any` | native | Dynamic fallback after named methods: an m_*-prefixed key reads the live schema field off the pawn's runtime class + inheritance chain, typed by the m_ name heuristic (m_iTeamNum special-cased uint8). Unknown -> nil. This is how scripts read arbitrary networked fields (pawn.m_iHealth, pawn.m_vecAbsOrigin). |

### Entity

`usertype` · tier `safe` — Generic game entity handle (shared read/glow surface with PlayerPawn).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `valid` | `:valid() -> boolean` | safe | True if this entity handle is still live/resolvable (O(1) live-set membership check). |
| `get_address` | `:get_address() -> integer` | safe | Raw entity pointer as an integer (identity key / debug). |
| `get_index` | `:get_index() -> integer` | safe | Entity entry index (slot); -1 if not live. Same value as PlayerPawn:get_index(). |
| `get_handle` | `:get_handle() -> integer\|nil` | safe | Full raw CHandle value (entry index + SERIAL bits); nil when not live. Identical in meaning to PlayerPawn:get_handle(). Use as a cache key when you need ENTITY IDENTITY: the serial makes a recycled entry slot a DIFFERENT key (cache miss) rather than a wrong hit on the dead occupant. CHANGED: the not-live return was 0, which is TRUTHY in Lua, so `if not h` never fired and every dead entity collided on key 0; it is now nil. The live VALUE is unchanged. |
| `get_class_name` | `:get_class_name() -> string` | safe | Real runtime schema class name (e.g. C_CitadelProjectile, CNPC_TrooperNeutral, CCitadelPlayerController); empty string if not live. |
| `get_raw_struct` | `:get_raw_struct() -> raw_struct\|nil` | safe | raw_struct over this entity's address + real runtime class chain, to read/write any schema field by name; nil if not live. |
| `as_pawn` | `:as_pawn() -> PlayerPawn\|nil` | safe | Upgrade this generic Entity to the rich PlayerPawn usertype if it is a Citadel player pawn, else nil. |
| `get_bbox` | `:get_bbox() -> table\|nil` | safe | Axis-aligned bounding box { mins, maxs } (plus world / screen sub-tables). |
| `get_bounding_box` | `:get_bounding_box() -> table\|nil` | safe | Native screen-space bounding rect { x, y, w, h } (C_BaseModelEntity::GetBoundingBox) - NOT the same as get_bbox. |
| `get_hitboxes` | `:get_hitboxes() -> table[]` | safe | Per-hitbox list: { center, bone_pos, mins, maxs, radius, capsule_a, capsule_b, capsule_radius, bone_index, shape } (no name field). |
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
| `get_animgraph_dbg` | `:get_animgraph_dbg() -> string` | safe | Generic-entity twin of PlayerPawn:get_animgraph_dbg — same chain-walk debug string, ALWAYS returned (never nil). Read-only. |
| `get_animgraph_dump` | `:get_animgraph_dump() -> table\|nil` | safe | Generic-entity twin of PlayerPawn:get_animgraph_dump (see that entry for the full field breakdown) — same hardcoded-client-scope AG2 pose-recipe blob + netvars-count dump. nil for a non-animating entity. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only. Read-only. |
| `get_graph_params` | `:get_graph_params() -> table\|nil` | safe | Generic-entity twin of PlayerPawn:get_graph_params (see that entry for the full field breakdown) — same GraphController2/ctrl candidate-base scan for CAnimGraph2ParamRefBase<T> blocks (hero_action_is_instant and friends). nil for a non-animating entity. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only, one-shot. Read-only. |
| `get_instant_cast` | `:get_instant_cast() -> {pctrl:integer, vtbl_ok:boolean, bound:boolean, idx:integer, gi_nonnull:boolean, value:integer}\|nil` | safe | Generic-entity twin of PlayerPawn:get_instant_cast (see that entry for the full chain + field breakdown) — reuses the same pawn+0x830->ctrl+0x1F8 ParamRef + vtbl-slot-9 vcall chain. Returns a table even when pCtrl is null/unbound; nil only on a hard fault. auto_parry reads enemies through the Entity path, not PlayerPawn, so this mirror is what makes the chain testable there. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only, one-shot. Read-only. |
| `get_melee_state` | `:get_melee_state() -> {size:integer, vec_count:integer, dumped:integer, raw_hex:string, hash:integer, state:string, is_heavy:boolean, is_light:boolean}\|nil` | safe | Generic-entity twin of PlayerPawn:get_melee_state (see that entry for the byte-family breakdown, cross-checked on a REAL enemy edge) — this is the path auto_parry reads enemies through. nil for a non-animating entity. DIAGNOSTIC ONLY (NOT wired into any feature). Game-thread only, one-shot. Read-only. |
| `GetLocalPlayer` | `GetLocalPlayer() -> PlayerPawn\|nil` | safe | Static (global Entity table): the local player's pawn. |
| `GetAllPlayers` | `GetAllPlayers() -> PlayerPawn[]` | safe | Static: every player pawn (same enumeration as entity_list.players). |
| `GetPlayerByIndex` | `GetPlayerByIndex(index: integer) -> PlayerPawn\|nil` | safe | Static: resolve a 0-based entity ENTRY index to a PlayerPawn, or nil. |
| `__index` | `:__index(key: string) -> any` | native | Dynamic: an m_*-prefixed key resolved against this entity's REAL runtime class chain and decoded at its TRUE schema width/type (ints/floats at real width, Vector, CHandle, full 8-byte pointers, char*/CUtlString as strings, Elem[N] and CUtlVector<Elem> as 1-based tables, pointer-to-class as a nested raw_struct). Non-string/unknown/unresolved -> nil. |
| `__newindex` | `:__newindex(key: string, value: any) -> nil` | native | Dynamic write-through to an m_*-prefixed schema field on this entity's class chain, typed at the field's TRUE width (a uint8/int16 write no longer clobbers neighbouring bytes); unresolved/unreadable/string/nested -> silent no-op. |

### Modifier

`usertype` · tier `safe` — Active modifier (buff/debuff) on an entity.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `name` | `.name: string` | safe |  |
| `duration` | `.duration: number` | safe |  |
| `stacks` | `.stacks: integer` | safe |  |

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
| `get_orig_button_state1` | `:get_orig_button_state1() -> integer` | safe |  |
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
| `Combo` | `:Combo(name: string, items: string[], default?: integer, icon?: string, tooltip?: string) -> MenuNode` | safe | Trailing string args after default are absorbed as (icon, tooltip); the first string is the icon, not the tooltip. |
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

### File

`usertype` · tier `native` — Open file handle (io / File API).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `read` | `:read(...) -> string` | native |  |
| `write` | `:write(data: string) -> boolean` | native |  |
| `close` | `:close()` | native |  |
| `is_open` | `:is_open() -> boolean` | native |  |
| `lines` | `:lines() -> string[]` | native | 1-indexed array of the remaining lines from the current cursor. |
| `seek` | `:seek(whence?: string, offset?: integer) -> integer` | native | Move the cursor. whence = "set"\|"cur"\|"end" (default "cur"); returns the new absolute position (-1 on failure). |
| `flush` | `:flush() -> boolean` | native | Flush buffered writes to disk. |

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

`usertype` · tier `native` — Typed read/write view over a native struct pointer.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get_int` | `:get_int(field: string) -> integer` | native |  |
| `get_float` | `:get_float(field: string) -> number` | native |  |
| `get_bool` | `:get_bool(field: string) -> boolean` | native |  |
| `get_vec` | `:get_vec(field: string) -> Vector3` | native |  |
| `set_int` | `:set_int(field: string, value: integer) -> nil` | native |  |
| `set_float` | `:set_float(field: string, value: number) -> nil` | native |  |
| `set_bool` | `:set_bool(field: string, value: boolean) -> nil` | native |  |
| `set_vec` | `:set_vec(field: string, value: Vector3) -> nil` | native |  |
| `offset_of` | `:offset_of(field: string) -> integer` | native |  |
| `class_name` | `:class_name() -> string` | native |  |
| `address` | `:address() -> integer` | native |  |
| `__index` | `:__index(field: string) -> any` | native | Read a schema field by name, typed by the m_ prefix heuristic (m_fl=float, m_b=bool, m_vec/ang/v=Vector3, m_h=handle, else int32); page-validated. Unresolved/null -> nil. |
| `__newindex` | `:__newindex(field: string, value: any) -> nil` | native | Write a schema field by name, typed by the m_ prefix heuristic; page-validated. Unresolved/unreadable -> silent no-op. |

### trace

`namespace` · tier `safe` — World/entity trace helpers (game-native + static mesh).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `line` | `trace.line(start: Vector3, finish: Vector3, opts?: table) -> table` | safe |  |
| `hull` | `trace.hull(start: Vector3, finish: Vector3, radius: number, opts?: table) -> table` | safe |  |
| `bullet` | `trace.bullet(start: Vector3, finish: Vector3, opts?: table) -> table` | safe |  |
| `bullet_hitbox` | `trace.bullet_hitbox(cmd_or_start: any, finish?: any, opts?: table) -> table` | safe |  |
| `visible` | `trace.visible(from: Vector3, to: Vector3, target?: PlayerPawn) -> boolean` | safe |  |

### mem

`namespace` · tier `native` — Raw memory access (read/write/scan/call).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `read_int` | `mem.read_int(address: integer) -> integer\|nil` | native |  |
| `read_int64` | `mem.read_int64(address: integer) -> integer\|nil` | native |  |
| `read_float` | `mem.read_float(address: integer) -> number\|nil` | native |  |
| `read_double` | `mem.read_double(address: integer) -> number\|nil` | native |  |
| `read_bool` | `mem.read_bool(address: integer) -> boolean\|nil` | native |  |
| `read_byte` | `mem.read_byte(address: integer) -> integer\|nil` | native |  |
| `read_ptr` | `mem.read_ptr(address: integer) -> integer\|nil` | native |  |
| `read_vec3` | `mem.read_vec3(address: integer) -> Vector3\|nil` | native |  |
| `read_string` | `mem.read_string(address: integer, max_len?: integer) -> string\|nil` | native |  |
| `write_int` | `mem.write_int(address: integer, value: integer) -> boolean` | native |  |
| `write_int64` | `mem.write_int64(address: integer, value: integer) -> boolean` | native |  |
| `write_float` | `mem.write_float(address: integer, value: number) -> boolean` | native |  |
| `write_double` | `mem.write_double(address: integer, value: number) -> boolean` | native |  |
| `write_bool` | `mem.write_bool(address: integer, value: boolean) -> boolean` | native |  |
| `write_byte` | `mem.write_byte(address: integer, value: integer) -> boolean` | native |  |
| `write_ptr` | `mem.write_ptr(address: integer, value: integer) -> boolean` | native |  |
| `write_vec3` | `mem.write_vec3(address: integer, value: Vector3) -> boolean` | native |  |
| `write_string` | `mem.write_string(address: integer, value: string) -> boolean` | native |  |
| `module_base` | `mem.module_base(module_name: string) -> integer\|nil` | native |  |
| `pattern_scan` | `mem.pattern_scan(module_name: string, pattern: string, offset?: integer) -> integer\|nil` | native |  |
| `get_call_target` | `mem.get_call_target(address: integer) -> integer\|nil` | native |  |
| `get_ptr_address` | `mem.get_ptr_address(address: integer, disp_offset?: integer, instr_len?: integer) -> integer\|nil` | native |  |
| `vfunc` | `mem.vfunc(instance: integer, index: integer) -> integer\|nil` | native |  |
| `call` | `mem.call(address: integer, ret_type: string, arg_types: string[], ...: any) -> any` | native |  |

### hooks

`namespace` · tier `native` — Function hooking (vmt / detour).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `vmt` | `hooks.vmt(instance: integer, slot_index: integer, detour: fun(args:table):any) -> HookHandle\|nil` | native |  |
| `detour` | `hooks.detour(target_addr: integer, detour: fun(args:table):any) -> HookHandle\|nil` | native |  |

### HookHandle

`usertype` · tier `native` — Handle returned by hooks.vmt / hooks.detour.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `remove` | `:remove() -> nil` | native |  |
| `call_original` | `:call_original(...: integer) -> integer\|nil` | native |  |
| `is_active` | `:is_active() -> boolean` | native |  |

### Schema

`namespace` · tier `safe` — Source2 schema access (enums / field offsets).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `enum` | `Schema.enum(name: string) -> table` | safe |  |
| `fields` | `Schema.fields(class: string) -> table` | safe |  |
| `offset` | `Schema.offset(class: string, field: string) -> integer` | safe |  |
| `field_info` | `Schema.field_info(class: string, field: string) -> table\|nil` | safe | Field metadata { offset, type, ... }. |
| `read` | `Schema.read(addr: integer, class: string, field: string) -> any\|nil` | safe | Read a schema field off a base address. |

### prediction

`namespace` · tier `safe` — Projectile / movement prediction over the cheat's solvers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `projectile` | `prediction.projectile(ability_or_params: any, ...) -> table\|nil` | safe |  |
| `aim_angles` | `prediction.aim_angles(eye: Vector3, target_pos: Vector3, target_vel: Vector3, speed: number, gravity: number, target_gravity?: number) -> table\|nil` | safe |  |
| `launch_position` | `prediction.launch_position(ability: Ability) -> Vector3\|nil` | safe |  |
| `launch_angle` | `prediction.launch_angle(ability: Ability) -> table\|nil` | safe |  |
| `fastest_projectile` | `prediction.fastest_projectile() -> table\|nil` | safe |  |
| `simulate_physics` | `prediction.simulate_physics(start_pos: Vector3, start_vel: Vector3, gravity: number, time: number, step?: number) -> table\|nil` | safe |  |

### nav

`namespace` · tier `safe` — Nav routing (grid A* over the static collision mesh).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `find_path` | `nav.find_path(start: Vector3, goal: Vector3) -> Vector3[]\|nil` | safe |  |
| `find_path_async` | `nav.find_path_async(start: Vector3, goal: Vector3) -> boolean` | safe |  |
| `get_route` | `nav.get_route() -> Vector3[]\|nil` | safe |  |

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
| `get_server_info` | `common.get_server_info() -> table` | safe | Snapshot of server/match info: map_name, map_group, max_players, player_count, tick_interval, tick_count, frame_count, current_time, is_in_game, match_time (+game_state/game_mode/match_mode/spectator_count/paused when GameRules is live). |
| `random_int` | `common.random_int(min: integer, max: integer) -> integer` | safe | Uniform integer in [min, max]. |
| `random_float` | `common.random_float(min: number, max: number) -> number` | safe | Uniform float in [min, max]. |
| `random_string` | `common.random_string(length: integer, charset?: string) -> string` | safe | Random string (default alphanumeric charset). |
| `execute_after` | `common.execute_after(delay: number, fn: function) -> integer\|nil` | safe | Fire fn once on the game thread after delay seconds (forwards to set_timeout). |
| `mark` | `common.mark(key: string)` | safe | Stamp key with the current game time. |
| `time_since` | `common.time_since(key: string) -> number` | safe | Seconds since key was last marked (huge if never). |
| `throttle` | `common.throttle(key: string, seconds: number) -> boolean` | safe | True (and re-stamps) once seconds elapse since the last success. |
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
| `get` | `HeroCfg.get() -> table` | safe | The LOCAL hero's whole persisted combo/aim config as a READ-ONLY table (writes raise): { hero_id, version, combo_key, combo_key_mode, show_visuals, lua_override, ability_order[4], abilities[4] = { enabled, manual_enabled, aim = {...}, combo_items = {...}, manual_items = {...}, weapon_override = {...} }, standalone }. Cached against the config version, so re-reading it every tick is free. Empty table when there is no local hero (test cfg.hero_id). |
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

### ComboOpt

`namespace` · tier `safe` — Declare your own option rows on the native Heroes page (per ability / per combo item / per always-on FEATURE) and read them back. Owner + hero are auto-filled.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `ability` | `ComboOpt.ability(slot: integer, hero?: integer) -> ComboOptScope` | safe | A declaration scope on signature ability `slot` (0..3) of the LOCAL hero — the rows appear in that ability's Aim & Targeting child. Pass `hero` to target a specific hero id, or 0 to show the rows on EVERY hero. |
| `item` | `ComboOpt.item(item: integer\|string, hero?: integer) -> ComboOptScope` | safe | A declaration scope on a combo ITEM — its EComboItem ordinal or its "upgrade_*" vdata token ("upgrade_metal_skin"). The rows appear in that item's combo card. Pass `hero` to target a specific hero id, or 0 for every hero. |
| `get` | `ComboOpt.get(key: string) -> any` | safe | The live value of one of THIS script's declared options (nil if it never declared `key`). Bool -> boolean, slider -> number, slider_int -> integer, enum -> the 1-based index into `choices`. Cheap enough to call every tick (cached handle + atomic read, no menu lock). ComboOpt.get(owner, key) reads another script's option. |
| `feature` | `ComboOpt.feature(spec: table)` | safe | Declare an always-on FEATURE: an enabled toggle (+ optional bind) plus 0..N sub-option rows. spec = { key, label, blurb?, default?, bind?, hero?, slot?, options={ { type="toggle"\|"slider"\|"slider_int"\|"dropdown"\|"color"\|"header"\|"hint", key, label?, tooltip?, default?, min?, max?, step?, fmt?, choices?, bind?, depends_on?, depends_value?, depends_not? }, ... } }. Read back with feature.enabled / feature.value. A bare `slider` with an integer `step` rounds (Int); otherwise it is a Float. `depends_on` names a sibling option key; `depends_not=true` inverts the depends_value test (show when the sibling != depends_value). Optional `slot` (0..3) binds the feature to an ability so the per-ability panel cross-links to it. |

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

### feature

`namespace` · tier `safe` — Read back an always-on FEATURE (declared via ComboOpt.feature): feature.enabled(key) and feature.value(key, opt). Owner + local hero auto-filled.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `enabled` | `feature.enabled(key: string, owner?: string) -> boolean` | safe | The enabled state of an always-on feature (false if it was never declared). Cheap every-tick read (cached handle + atomic). |
| `value` | `feature.value(key: string, opt: string, owner?: string) -> any` | safe | The live value of a feature sub-option, typed by kind: toggle->boolean, slider->number, slider_int->integer, dropdown->1-based index, color->32-bit RGBA integer. nil if never declared. |
| `color` | `feature.color(key: string, opt: string, owner?: string) -> integer, integer, integer, integer` | safe | A `color` sub-option decomposed into r, g, b, a (0..255) — splat straight into Color(...). Opaque white when unresolved. |

### Panorama

`namespace` · tier `safe` — Panorama UI control (run JS / find/create/restyle HUD panels). Open to ALL scripts: JS runs in the game's Panorama UI layer, not raw process memory / native code, so it is Safe-tier (not gated like mem/hooks/native/ffi).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `available` | `Panorama.available() -> boolean` | safe | Panorama reachable now (game thread, engine+panel up). |
| `run_script` | `Panorama.run_script(js: string, panel?: PanoramaPanel) -> boolean` | safe | Run Panorama JS (primary). |
| `run_js` | `Panorama.run_js(js: string, panel?: PanoramaPanel) -> boolean` | safe | Alias of run_script. |
| `root` | `Panorama.root() -> PanoramaPanel` | safe | HUD root. |
| `context` | `Panorama.context() -> PanoramaPanel` | safe | $.GetContextPanel(). |
| `find` | `Panorama.find(id: string) -> PanoramaPanel` | safe | root.FindChildTraverse(id). |
| `create` | `Panorama.create(type: string, parent?: PanoramaPanel, id?: string) -> PanoramaPanel` | safe | $.CreatePanel (auto-ids if omitted). |

### PanoramaPanel

`usertype` · tier `safe` — Handle to a Panorama panel (JS selector).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `find_child` | `:find_child(id: string) -> PanoramaPanel` | safe |  |
| `set_text` | `:set_text(text: string) -> PanoramaPanel` | safe |  |
| `set_style` | `:set_style(prop: string\|table, value?: string) -> PanoramaPanel` | safe |  |
| `add_class` | `:add_class(name: string) -> PanoramaPanel` | safe |  |
| `remove_class` | `:remove_class(name: string) -> PanoramaPanel` | safe |  |
| `set_visible` | `:set_visible(visible: boolean) -> PanoramaPanel` | safe |  |
| `set_attribute` | `:set_attribute(name: string, value: string) -> PanoramaPanel` | safe |  |
| `run_script` | `:run_script(js: string) -> PanoramaPanel` | safe | Run JS with `self` bound to this panel. |
| `remove` | `:remove() -> PanoramaPanel` | safe | DeleteAsync. |
| `delete` | `:delete() -> PanoramaPanel` | safe | Alias of remove. |
| `id` | `:id() -> string` | safe |  |
| `valid` | `:valid() -> boolean` | safe | Structural (has selector). |
| `get_attribute` | `:get_attribute(name: string) -> nil` | safe | RE gap: no readback; always nil. |
| `children` | `:children() -> table` | safe | RE gap: no readback; empty table. |

### native

`namespace` · tier `native` — Curated native-access primitives (interfaces/vfuncs/pattern-scan/netvar offsets). TRUSTED/local only — stripped for untrusted scripts.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `create_interface` | `native.create_interface(module_name: string, version: string) -> integer\|nil` | native | CaptureFactory(module).CreateInterface(version). |
| `get_vfunc` | `native.get_vfunc(instance: integer, index: integer) -> integer\|nil` | native | Read a vtable slot (same contract as mem.vfunc). |
| `call_vfunc` | `native.call_vfunc(instance: integer, index: integer, ret_type: string, arg_types: string[], ...: any) -> any` | native | Resolve + call a vtable slot with instance as implicit arg0 (<=3 more args). |
| `find_pattern` | `native.find_pattern(module_name: string, pattern: string, offset?: integer) -> integer\|nil` | native | Same contract as mem.pattern_scan. |
| `find_pattern_range` | `native.find_pattern_range(pattern: string, start_addr: integer, end_addr: integer, offset?: integer) -> integer\|nil` | native | Scan an explicit [start,end) range (256MB cap). |
| `get_netvar_offset` | `native.get_netvar_offset(class_name: string, field_name: string) -> integer\|nil` | native | GetSchemaOffset()->GetOffset(class, field). |
| `get_call_target` | `native.get_call_target(address: integer) -> integer\|nil` | native | Same guarded CALL-rel32 resolve as mem.get_call_target. |
| `get_ptr_address` | `native.get_ptr_address(address: integer, disp_offset?: integer, instr_len?: integer) -> integer\|nil` | native | Same guarded RIP-relative resolve as mem.get_ptr_address. |
| `module_base` | `native.module_base(module_name: string) -> integer\|nil` | native | Same primitive as mem.module_base. |

### ffi

`namespace` · tier `native` — Curated typed-call FFI bridge (bounded scalar types, allowlisted modules; NOT real ffi.cdef parsing). TRUSTED/local only — stripped for untrusted scripts.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `load` | `ffi.load(module_name: string) -> FFILib\|nil` | native | Resolve an ALREADY-LOADED, allowlisted module handle (never loads a new DLL). |
| `func` | `ffi.func(addr: integer, ret_type: string, arg_types: string[]) -> FFICallable\|nil` | native | Build a typed callable over a raw address. |
| `cast` | `ffi.cast(type: string, address: integer) -> FFIScalar\|nil` | native | Typed read/write VIEW into EXISTING memory (scalar types only). |
| `new` | `ffi.new(type: string) -> FFIScalar\|nil` | native | Typed read/write VIEW into a freshly allocated, zeroed, session-lifetime buffer. |

### FFILib

`usertype` · tier `native` — Handle to an allowlisted loaded module from ffi.load.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `func` | `:func(export_name: string, ret_type: string, arg_types: string[]) -> FFICallable\|nil` | native | Resolve export_name off this lib's module, then build a typed callable. |

### FFICallable

`usertype` · tier `native` — Typed callable native function pointer; invoke via ().

| Member | Signature | Tier | Description |
|---|---|---|---|
| `__call` | `:__call(...: any) -> any` | native | Invoke via callable(...); same SpoofCall path as mem.call/native.call_vfunc. |

### FFIScalar

`usertype` · tier `native` — A scalar C value view (cast) or allocation (new).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `get` | `:get() -> any` | native | Typed read (int/int64/uint/ptr/bool/float32/float64 per the scalar kind). |
| `set` | `:set(value: any) -> boolean` | native | Typed write; false for float32/float64 (read-only) or a bad address. |
| `addr` | `:addr() -> integer` | native | The underlying address. |

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
| `is_ability_ready` | `HERO_LIB.is_ability_ready(ability: Ability) -> boolean` | safe |  |
| `is_ability_in_cd` | `HERO_LIB.is_ability_in_cd(ability: Ability) -> boolean` | safe |  |
| `is_ability_in_cast_delay` | `HERO_LIB.is_ability_in_cast_delay(ability: Ability) -> boolean` | safe |  |
| `is_ability_in_self_cast_delay` | `HERO_LIB.is_ability_in_self_cast_delay(ability: Ability) -> boolean` | safe |  |
| `get_scaled_property` | `HERO_LIB.get_scaled_property(ability: Ability, key: string) -> number` | safe |  |
| `dump_ability` | `HERO_LIB.dump_ability(ability: Ability)` | safe | GROUND-TRUTH AUDIT AID. Appends this ability/item class's REAL authored property set (every VData-enumerated key + its scaled value) to C:\Avalanche\Config\ability_properties_dump.txt, one section per class. Deduped by class name in C++, so repeat/per-tick calls are a cheap early return (no per-tick I/O). Game-thread only. Use to discover exact property names for readers. |
| `get_cast_range` | `HERO_LIB.get_cast_range(ability: Ability) -> number` | safe |  |
| `get_cast_delay_fraction` | `HERO_LIB.get_cast_delay_fraction(ability: Ability) -> number` | safe |  |
| `has_ability` | `HERO_LIB.has_ability(name: string) -> boolean` | safe | True if the local hero owns an ability whose class matches `name` (AbilityComponent class-name scan). |
| `is_on_ground` | `HERO_LIB.is_on_ground(pawn?: PlayerPawn) -> boolean` | safe |  |
| `get_stamina` | `HERO_LIB.get_stamina() -> number` | safe |  |
| `get_dash_jump_state` | `HERO_LIB.get_dash_jump_state(pawn: PlayerPawn) -> table\|nil` | safe | Engine dash-jump window { can_dash_jump, window_start, window_end, consecutive_air_dashes, ok }. Same read the INNATE.DASH_JUMP precondition uses. |
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
| `get_target_pos` | `HERO_LIB.get_target_pos(target: PlayerPawn) -> Vector3` | safe |  |
| `predict_target` | `HERO_LIB.predict_target(target: PlayerPawn) -> Vector3` | safe |  |
| `get_origin` | `HERO_LIB.get_origin(pawn: PlayerPawn) -> Vector3` | safe |  |
| `get_velocity` | `HERO_LIB.get_velocity(pawn: PlayerPawn) -> Vector3` | safe |  |
| `get_heroes_in_radius` | `HERO_LIB.get_heroes_in_radius(pos: Vector3, radius: number) -> PlayerPawn[]` | safe | radius is in game UNITS, NOT meters (convert a meters value with HERO_LIB.METERS_TO_UNITS first). |
| `entities_by_class` | `HERO_LIB.entities_by_class(class_slug: string, opts?: table) -> table[]\|nil` | safe | By-CLASS entity query over the entity cache — the ONLY path to a non-pawn entity (turret / trap / soul / breakable / projectile). `class_slug` is an EntityClassRegistry slug (the value the Heroes page's "Entity class" target dropdown stores). Rows are NEAREST FIRST: { pos (the class's declared aim point), origin, dist (units), handle, team, enemy, mine (the local pawn threw/owns it), visible (only when opts.require_visible), class, pawn (the `players` class only) }. opts = { origin:Vector3, max_range_u, team="enemy"\|"ally"\|"any", mine, require_visible, limit }. Returns NIL (not an empty table) when the slug is not a known class, so a bad config reports itself. |
| `should_ignore_target` | `HERO_LIB.should_ignore_target(pawn: PlayerPawn) -> boolean` | safe | Does the user's IGNORE list reject this pawn? The same ScriptHelpers::ShouldIgnoreTarget filter find_combo_target applies to every candidate. Any pick made OUTSIDE find_combo_target (a radius scan, a fallback) must ask this or it can return a hero the user told the aimbot to ignore. An invalid pawn ignores (fail-closed). |
| `get_fov_to_pos` | `HERO_LIB.get_fov_to_pos(pos: Vector3) -> number` | safe |  |
| `is_pos_within_fov` | `HERO_LIB.is_pos_within_fov(pos: Vector3, fov: number) -> boolean` | safe |  |
| `no_obs_to_pos` | `HERO_LIB.no_obs_to_pos(pos: Vector3) -> boolean` | safe |  |
| `no_obs_to_target` | `HERO_LIB.no_obs_to_target(target: PlayerPawn) -> boolean` | safe |  |
| `get_hitbox_aim` | `HERO_LIB.get_hitbox_aim(target: PlayerPawn, hitbox_bits: integer) -> Vector3\|nil` | safe | Resolve a Hitbox-widget bitfield (bits 0-4 enabled Head/Neck/Torso/Arms/Legs, bits 5-9 priority) to the picked bone's world position. nil = bones not resolvable this frame. |
| `resolve_aim_point` | `HERO_LIB.resolve_aim_point(target: PlayerPawn, opts: table) -> Vector3\|nil` | safe | The Heroes-page "Point mode" aim point, all five modes: opts = { mode = 0 Hitboxes \| 1 Bone \| 2 Height offset \| 3 Closest surface \| 4 Origin, bits (the hitbox bitfield, modes 0/3), bone (a model bone NAME, mode 1), z (units, mode 2) }. Mode 3 returns the point on the picked hitbox's SURFACE nearest the cast ray — the aim point that minimises the PSilent camera-position offset. nil = unresolvable; the caller keeps its own fallback. |
| `predict_projectile` | `HERO_LIB.predict_projectile(check_obstruction: boolean, info_from: integer, sim_tier: integer, aim_to_pos: integer, target: PlayerPawn, ability: Ability, caster?: PlayerPawn, opts?: table) -> (Vector3\|nil, Vector3, table, table, number, boolean)` | safe | Projectile lead solver. ARG ORDER IS EXACT: check_obstruction (ignored), info_from = ENUM_PPS_INFO_FROM (0 PROJECTILE / 1 GUN), sim_tier = ENUM_MV_SIM_TYPE, aim_to_pos = ENUM_PPS_AIM_TO_POS, then target, ability, optional caster (defaults to local pawn). Trailing opts = { speed=, radius=, hitbox= } — the hitbox bitfield goes HERE, NOT positionally. Returns aim_pos, sim_pos, traj, path, lead_time, blocked. aim_pos is nil when there is no solution. lead_time (5th) = PHYSICAL flight-time lead in SECONDS, NO ping term (native prediction is latency-blind by design; add net_channel.latency yourself for total lead). blocked (6th) = TRUE when the shot was VETOED: its trajectory (swept with the ability's real radius, arc-aware) would hit world geometry before reaching the target, or the target won't be hittable at the predicted impact (rounded a corner). blocked=true means DO NOT CAST (hold/skip); a plain nil aim_pos with blocked=false is a benign miss (fall back to a static point). |
| `predict_projectile_simulated` | `HERO_LIB.predict_projectile_simulated(check_obstruction: boolean, info_from: integer, sim_tier: integer, aim_to_pos: integer, target: PlayerPawn, ability: Ability, caster?: PlayerPawn, opts?: table) -> (Vector3\|nil, Vector3, table, table, number, boolean)` | safe | ALIAS of predict_projectile — the SAME function pointer (&PredictProjectileImpl), not a separate simulated solver. Same exact 8-arg signature (hitbox goes in the trailing opts table, not positionally). 5th return lead_time = flight-time lead in SECONDS, no ping term. 6th return blocked = the collision/visibility VETO (true = trajectory hits world geometry / target not hittable at impact = DO NOT CAST). |
| `hull_projectile_will_hit` | `HERO_LIB.hull_projectile_will_hit(target: PlayerPawn, pos: Vector3, radius: number) -> boolean` | safe |  |
| `simulate_pawn_movement` | `HERO_LIB.simulate_pawn_movement(target: PlayerPawn, sim_type: integer, stopCb?: function) -> table\|nil` | safe | Single-tick movement seed { origin, velocity, on_ground }. sim_type: 0=SimulatePhysics (gravity arc + air-drag), 1=Linear. Optional stopCb per the lib closure contract. |
| `simulate_movement_for_duration` | `HERO_LIB.simulate_movement_for_duration(target: PlayerPawn, duration: number, sim_type?: integer) -> table\|nil` | safe |  |
| `rotate_movement` | `HERO_LIB.rotate_movement(vec: Vector3, degrees: number) -> Vector3` | safe |  |
| `is_untargetable` | `HERO_LIB.is_untargetable(pawn: PlayerPawn) -> boolean` | safe |  |
| `is_in_ethereal_shift` | `HERO_LIB.is_in_ethereal_shift(pawn: PlayerPawn) -> boolean` | safe |  |
| `aim_psilent_default` | `HERO_LIB.aim_psilent_default(cmd: UserCmd, target_pos: Vector3, ...) -> boolean` | safe | Optional trailing Ability names the cast (bus owner + early release). |
| `aim_psilent` | `HERO_LIB.aim_psilent(cmd: UserCmd, target_pos: Vector3, ...) -> boolean` | safe |  |
| `psilent_bus_settled` | `HERO_LIB.psilent_bus_settled() -> boolean` | safe | PSilent camera is free: no cast in flight. Gate a combo step on it. |
| `cast_ability` | `HERO_LIB.cast_ability(cmd: UserCmd, slot: integer)` | safe |  |
| `is_heavy_melee` | `HERO_LIB.is_heavy_melee(pawn: PlayerPawn) -> boolean` | safe | True while this pawn is mid heavy-melee. Checks the modifier STATE first (works on ENEMIES), then falls back to the HoldMelee ability's attack type/state (more precise, but only ever populated for the LOCAL/spectated player — see is_heavy_melee_charging). |
| `is_heavy_melee_charging` | `HERO_LIB.is_heavy_melee_charging(pawn: PlayerPawn) -> boolean` | safe | True while this pawn is winding up / dashing a HEAVY melee. THE signal to arm an auto-parry on, and the only one that works on ENEMIES. Derived from CModifierCache's state mask (MODIFIER_STATE_IS_IN_CHARGE_MELEE=293 / IN_SLIDE_CHARGED_MELEE_ATTACK=193, both verified against the live client.dll enum table). Do NOT use HERO_LIB.melee_state().type/.state for an enemy: those fields are MNetworkUserGroup='LocalPlayerOwnerAndObserversExclusive', i.e. the server only sends them to the ability's OWNER and that owner's spectators, so for an enemy they read 0/None forever at a perfectly correct offset. Every other field on CCitadel_Ability_HoldMelee (m_flStateStartTime, m_flDashStartTime, m_nLightChainCount) has the same user group, and m_bCreatedChargeEffects/m_angForced/m_vGoalDir are not networked at all — there is no readable field alternative. |
| `modifier_state_bits` | `HERO_LIB.modifier_state_bits(pawn: PlayerPawn) -> integer[]` | safe | DIAGNOSTIC: every ENABLED modifier-state ordinal on this pawn, from CModifierCache's snapshot. Use it to PROVE which state a behaviour actually sets rather than guessing an ordinal. Not for hot paths. |
| `melee_range_tier` | `HERO_LIB.melee_range_tier(pawn: PlayerPawn) -> integer` | safe | This pawn's melee-range ITEM tier: 0 = none, 1 = Melee Charge, 2 = Crushing Fists. These extend a heavy melee's LUNGE DISTANCE (not its duration), so an auto-parry must add the tier's reach bonus when predicting where the punch lands — a Crushing Fists holder out-reaches the base lunge by ~140u. Non-stacking: a Crushing Fists holder also carries the Melee Charge modifier, so this returns the MAX tier and you add ONE bonus. Read from CModifierCache's once-per-frame game-thread walk (substring-matched on the real item modifier names) — do NOT try to reproduce it with pawn:has_modifier(), which is EXACT string equality and will silently always miss. |
| `melee_state` | `HERO_LIB.melee_state(pawn: PlayerPawn) -> table\|nil` | safe | { state = EMeleeHold_AttackState, type = EMeleeHold_AttackType, start_time (game seconds), charging = boolean } off the pawn's HoldMelee ability, or nil if it has none. WARNING: state/type/start_time are ZERO FOR ENEMIES — they are MNetworkUserGroup='LocalPlayerOwnerAndObserversExclusive', so the server only sends them to the ability's owner and that owner's spectators; they are populated only for the LOCAL/spectated player. `charging` is the modifier-derived field that DOES work on enemies (same source as is_heavy_melee_charging) — use that, or is_heavy_melee_charging(pawn). |
| `telepunch_state` | `HERO_LIB.telepunch_state(ability: Ability) -> integer` | safe | Viscous Telepunch state (ETelepunchState_t) read as EXACTLY one byte — the generic Ability.__index over-reads this uint8_t enum as int32 (folds in 3 adjacent bytes). Pass the CCitadel_Ability_Viscous_Telepunch ability; 0 (None) if it isn't that ability / is nil. |
| `parry_ready` | `HERO_LIB.parry_ready() -> boolean` | safe | Local parry ability is off cooldown. The 'off cooldown' half of the old innate_ready(INNATE.PARRY). |
| `parry_blocked` | `HERO_LIB.parry_blocked() -> boolean` | safe | A local parry press would be wasted right now: synced move / a parry-blocking modifier (stun, invis) / on a zipline. The 'blocked' half of innate_ready(INNATE.PARRY). |
| `has_any_particle` | `HERO_LIB.has_any_particle(pawn: PlayerPawn, ...: string\|string[]) -> boolean` | safe | Any substring matches a particle recently created on this pawn (the shared recent-particle tracker, TTL'd). Accepts EITHER an array table `has_any_particle(p, {"a","b"})` OR varargs strings `has_any_particle(p, "a", "b")` — both shapes work on every has_any_particle binding. Empty/absent list => any recent particle at all. For anything TIMING-sensitive use PlayerPawn:get_particle_age instead: this stays true for the tracker's full 3s TTL. |
| `get_combo_fov` | `HERO_LIB.get_combo_fov() -> number` | safe |  |
| `is_target_within_cone` | `HERO_LIB.is_target_within_cone(target: PlayerPawn, fov_deg: number) -> boolean` | safe | BANNED / DEPRECATED — distance-blind and tests the wrong quantity (the 5-arg form takes a COSINE, not degrees). Use HERO_LIB.psilent_reach_ok(lp, cmd, target_pos[, ability]) to gate whether a cast can actually reach the target. |
| `script_aim_on_target` | `HERO_LIB.script_aim_on_target() -> boolean` | safe | Has the shared script VISIBLE aimbot reached the point it would itself fire at (crosshair in the deadzone, not mid-flick)? Meaningful only right AFTER driving it this tick (Bus.steer_normal / a hybrid drive), so drive THEN ask. This is Hybrid's handoff trigger: run the normal aimbot to its own fire point, then let psilent deliver — a single human flick that eases to a stop, instead of the reach-boundary stop/start flip. |
| `is_channeling_specific_abilities` | `HERO_LIB.is_channeling_specific_abilities(...) -> boolean` | safe |  |
| `is_in_cast_delay_specific_abilities` | `HERO_LIB.is_in_cast_delay_specific_abilities(...) -> boolean` | safe |  |
| `find_combo_target` | `HERO_LIB.find_combo_target(lp: PlayerPawn\|nil, opts?: table) -> PlayerPawn\|nil` | safe | The combo-target selector: eye position and view angles are resolved INTERNALLY (the leading pawn/cmd arg is accepted for call-shape compatibility and otherwise ignored). opts = { max_range_m=50, bone="spine_2", require_visible=true, combo_fov=180 } (combo_fov 180 = no cone gate, closest-in-range). Honors the global Aimbot Target Priority dropdown, the user's ignore rules and the visibility gate — every candidate is filtered, so any pick made OUTSIDE it must ask should_ignore_target. NOTE: the native declares THREE positional slots to absorb legacy call shapes; the engine passes an explicit trailing nil for the unused second config so AvaLua's arg reader does not flag a missing slot. |
| `can_combo` | `HERO_LIB.can_combo() -> boolean` | safe |  |
| `passive_items` | `HERO_LIB.passive_items() -> boolean` | safe |  |
| `combo_active` | `HERO_LIB.combo_active(bind: MenuNode) -> boolean` | safe | Combo running this tick (hold/perma). |
| `combo_active_latched` | `HERO_LIB.combo_active_latched(bind: MenuNode, timeout?: number) -> boolean` | safe | One-press-runs-the-whole-combo latch. |
| `combo_latch` | `HERO_LIB.combo_latch(state: table, active_now: boolean, timeout?: number) -> boolean` | safe | Explicit latch for step machines. |
| `combo_keepalive` | `HERO_LIB.combo_keepalive(state?: table)` | safe | Hold the stuck-clock during a long charge. |
| `combo_interrupt_status` | `HERO_LIB.combo_interrupt_status() -> string\|nil` | safe | "fatal"\|"blocked"\|nil. |
| `clear_sticky_target` | `HERO_LIB.clear_sticky_target()` | safe | Drop the persisted combo target + generation. |
| `run_combo_sequence` | `HERO_LIB.run_combo_sequence(state: table, fns: function[]) -> boolean` | safe | Step-cycling one-per-tick fall-through. |
| `is_busy` | `HERO_LIB.is_busy() -> boolean` | safe | Local hero mid-action (BUSY_WITH_ACTION). |
| `is_cc` | `HERO_LIB.is_cc() -> boolean` | safe | Local hero HARD-BLOCKED (stunned/silenced/asleep). The other half of combo_interrupt_status()'s "blocked": blocked <=> is_busy() or is_cc(). |
| `recently_cast` | `HERO_LIB.recently_cast(ability: Ability, recovery?: number) -> boolean` | safe | Charge-dump spacing guard. |
| `fired_this_combo` | `HERO_LIB.fired_this_combo(ability: Ability) -> boolean` | safe | One fire per ability per discrete combo. |
| `ability_in_range` | `HERO_LIB.ability_in_range(lp: PlayerPawn, ability: Ability, target: PlayerPawn, extra_m?: number) -> boolean` | safe | Real cast range + slack (fail-open). |
| `lock_on_ready` | `HERO_LIB.lock_on_ready(lp: PlayerPawn, cmd: UserCmd, ability: Ability, target: PlayerPawn, extra_m?: number) -> boolean` | safe | Range AND camera-position psilent reach. |
| `cast_origin` | `HERO_LIB.cast_origin(lp: PlayerPawn) -> Vector3` | safe | ability_cast attachment (or origin+eye). |
| `get_ability_range` | `HERO_LIB.get_ability_range(ability: Ability) -> number` | safe | Real cast range in UNITS. |
| `lethal_estimate` | `HERO_LIB.lethal_estimate(target: PlayerPawn, damage: number) -> boolean` | safe | damage >= HP+barrier. |
| `is_lethal` | `HERO_LIB.is_lethal(ability: Ability, target: PlayerPawn, seconds_until_hit: number?) -> boolean` | safe | Ability resolved damage vs effective HP (post-resist damage vs current HP+barrier). Optional seconds_until_hit projects the target's HP forward by its passive regen over that window (a charge/scope hold, projectile travel) so an execute won't fire on a target that heals out of lethal range by impact; omit/0 = current HP. |
| `lethality` | `HERO_LIB.lethality(ability: Ability, target: PlayerPawn, seconds_until_hit: number?) -> table\|nil` | safe | The NUMBERS behind is_lethal: { damage (post-resist, one FULL cast, INCLUDES the headshot bonus), headshot_bonus (the head-shot-only slice of damage; damage-headshot_bonus = the BODY-shot damage; 0 if no headshot mechanic), hp (current+barrier, regen-projected over seconds_until_hit), remaining, lethal, valid }. Lets a charge-up ability invert 'how much charge kills this target' and lets a sniper choose center-mass vs head by whether the body shot alone is lethal. Optional seconds_until_hit matches is_lethal (heal projection). valid=false => damage unresolvable, do not gate. |
| `headshot_cap_ok` | `HERO_LIB.headshot_cap_ok(max_percent: number) -> boolean` | safe | May a script aim at the HEAD right now? The same stat test the aimbot's own bone selection applies (CanTargetHeadBasedOnDamageStats); false => drop Head+Neck from the mask. |
| `vdata_property` | `HERO_LIB.vdata_property(ability: Ability, vdata_class: string, field: string) -> number\|nil` | safe | A float field on the ability's VDATA, by schema CLASS + NAME (e.g. "CAbilityHornetSnipeVData", "m_flMinScopeTimeToShoot"). ability:get_vdata() only projects m_projectileInfo/m_WeaponInfo, so every other authored VData number is unreachable without this. The class name is explicit because a VData object carries no schema binding to ask. Offset resolved through the LIVE schema. nil = unknown class/field. |
| `maybe_light_melee` | `HERO_LIB.maybe_light_melee(cmd: UserCmd, chance: number, key?: string) -> boolean` | safe | Roll-once light-melee humanizer. |
| `reset_light_melee` | `HERO_LIB.reset_light_melee(key: string)` | safe | Open a fresh melee roll window. |
| `press_ability` | `HERO_LIB.press_ability(cmd: UserCmd, slot: integer)` | safe | Press a signature slot's IN_ABILITYn. |
| `slot_ability_bit` | `HERO_LIB.slot_ability_bit(slot: integer) -> number` | safe | slot 0..3 -> IN_ABILITYn bit. |
| `meters_to_units` | `HERO_LIB.meters_to_units(m: number) -> number` | safe |  |
| `begin_combo_tick` | `HERO_LIB.begin_combo_tick(cmd: UserCmd, hero_id: integer, enable: boolean, bind: MenuNode, opts?: table) -> PlayerPawn\|nil, PlayerPawn\|nil` | safe | Createmove prologue: returns lp,target. |
| `run_projectile_ability` | `HERO_LIB.run_projectile_ability(cmd: UserCmd, target: PlayerPawn, lp: PlayerPawn, opts: table) -> boolean` | safe | Full projectile-ability pipeline in one call. |
| `abilities_ready` | `HERO_LIB.abilities_ready() -> boolean` | safe | INIT-TIMING honesty signal. False in the brief post-inject / post-hero-swap window where the local pawn already exists (hero-id resolution already works then) but the game hasn't yet populated its ability component with slotted signature abilities — the exact gap behind 'can_use_ability/ability_true_cooldown read wrong right after injecting'. LIVE, not cached: nothing to call to force it — once this returns true, re-querying can_use_ability/ability_true_cooldown/can_activate() returns correct data on its own. Checks only the 4 signature slots (every hero always has them); items are excluded since an empty item slot can be legitimately unowned all match. |
| `can_use_ability` | `HERO_LIB.can_use_ability(slot: integer) -> boolean` | safe | Authoritative yes/no for signature slot 1..4 (game's own cast-validity). slot is 1-INDEXED here (as are can_use_item / ability_true_cooldown / item_true_cooldown) — note that ability_slot(), SlotInputBit and the aim `slot` arg are 0-INDEXED (0..3). |
| `can_use_item` | `HERO_LIB.can_use_item(slot: integer) -> boolean` | safe | Authoritative yes/no for active-item slot 1..4. |
| `ability_true_cooldown` | `HERO_LIB.ability_true_cooldown(slot: integer) -> number` | safe | Seconds until signature slot 1..4 is usable again (0 = now; >0 = next USABLE CHARGE). |
| `item_true_cooldown` | `HERO_LIB.item_true_cooldown(slot: integer) -> number` | safe | Seconds until active-item slot 1..4 is usable again (0 = now; >0 = next USABLE CHARGE). |
| `can_place_ability_on` | `HERO_LIB.can_place_ability_on(slot: integer, entity: PlayerPawn) -> boolean` | safe | Targeting validity for signature slot 1..4 on a candidate entity: team/type (ally/enemy/self) + range + cone + LOS, from the ability's own vdata. Per-target companion of can_use_ability. READ-ONLY. |
| `can_place_item_on` | `HERO_LIB.can_place_item_on(slot: integer, entity: PlayerPawn) -> boolean` | safe | Targeting validity for active-item slot 1..4 on a candidate entity (same rules as can_place_ability_on). Per-target companion of can_use_item. READ-ONLY. |
| `owns_item` | `HERO_LIB.owns_item(token: string) -> boolean` | safe | Local hero owns exactly this active item now. `token` is the `upgrade_<name>` grid id, resolved by the ONE exact/anchored/fail-closed item resolver (ScriptHelpers::FindItemByToken). |
| `item_ready` | `HERO_LIB.item_ready(token: string) -> boolean` | safe | Owned AND off cooldown / ready (validated readiness path). |
| `item_range` | `HERO_LIB.item_range(token: string) -> number, number` | safe | cast_range, aoe_radius for the OWNED item. BOTH in game UNITS (cast_range now normalised through the same resolver get_cast_range uses; aoe via get_aoe_radius). (0,0) if not owned. Compare against Distance() in units. |
| `use_item_slot` | `HERO_LIB.use_item_slot(cmd: UserCmd, token: string, target_pos?: Vector3) -> boolean` | safe | Fire the OWNED item by its CURRENT active-item slot bit (robust to runtime slot moves). If target_pos is given and non-zero the cast first wins a slot on the PSilent bus (camera POSITION only); a busy bus presses NOTHING and returns false (retry next tick). false = not owned/ready/active-item. |
| `use_item` | `HERO_LIB.use_item(cmd: UserCmd, ability: Ability) -> boolean` | safe | Fire an active ITEM instantly (self/AOE buff): resolve the item's active-item slot -> input bit and press it. false = not an active item / invalid. |
| `use_item_targeted` | `HERO_LIB.use_item_targeted(cmd: UserCmd, ability: Ability, target_pos: Vector3) -> boolean` | safe | Take a slot on the PSilent bus toward target_pos for the item's slot bit, then press it (targeted item lands on the enemy). Camera POSITION only. false = not an item / bus busy (press nothing, retry). |
| `psilent_reach_ok` | `HERO_LIB.psilent_reach_ok(lp: PlayerPawn, cmd: UserCmd, target_pos: Vector3, ability_or_slot?: Ability\|integer) -> boolean` | safe | THE sanctioned reach test: can the camera-position spoof actually CENTRE target_pos this tick? Computed by the SAME solver the applier uses (offset from the commanded-camera eye, the engine-clamp anchor) so 'can I hit?' matches 'will the spoof centre it?'. Returns true only when the needed offset <= active PSilent reach * 0.9 (a small honest-edge safety margin, so marginal shots the engine would clamp short are HELD, not fired blind). Only target_pos is required; the optional Ability/0..3 slot scopes the reach to that ability's override. USE THIS INSTEAD OF is_target_within_cone (distance-blind, wrong quantity). |
| `mark_combo_active` | `HERO_LIB.mark_combo_active()` | safe | Pulse each tick the Combo Key is held so the Bind Island shows the hero script as active only while its combo runs (key-press -> cast tail), not always-on once loaded. |
| `reset_combo_sticky` | `HERO_LIB.reset_combo_sticky()` | safe | Reset the C++ sticky combo target so the next combo re-acquires by configured priority (call on combo end). Without it the selector holds the previous combo's target across presses. |
| `ability_slot` | `HERO_LIB.ability_slot(ability: Ability) -> integer` | safe | The ability's LIVE signature slot 0..3 (= ability 1..4) read from m_eAbilitySlot, or -1 if not a signature ability. Press/aim the slot the game ACTUALLY put the ability in — Deadlock reorders abilities between builds, so a hardcoded slot fires the wrong button. 0-INDEXED. |
| `get_aoe_radius` | `HERO_LIB.get_aoe_radius(ability: Ability) -> number` | safe | Ability AOE radius in game UNITS (upgrade-aware, force-populated; Start/EndRadius items report their real radius). 0 if none. |
| `entity_pos_by_name` | `HERO_LIB.entity_pos_by_name(name: string) -> Vector3\|nil` | safe | World position of the first entity whose class name contains `name` (case-insensitive substring over the live entity system). nil if none / not a string. |
| `interval_per_tick` | `HERO_LIB.interval_per_tick() -> number` | safe | Seconds per simulation tick (guarded; ~1/64). The lib's timing primitive. |
| `lp_hero_name` | `HERO_LIB.lp_hero_name() -> string` | safe | Ground-truth local hero name "<table>\|<designer>" for diagnostics (mirrors the PlayerESP hero-icon path). |
| `diag` | `HERO_LIB.diag(...)` | safe | Write ONE deduped line to C:\Avalanche\avalan-debug.log (file-only, never console). Args joined by spaces; each UNIQUE line written once. NO-OP in the protected release build. |
| `log` | `HERO_LIB.log(...)` | safe | Script-side diagnostic sink (stripped to a no-op in C++; not a native error channel). |
| `dev_mode` | `HERO_LIB.dev_mode() -> boolean` | safe | Is verbose dev surfacing on? OFF by default (also settable at boot via env AVALANCHE_LUA_DEVMODE). When on, U.log lines + the full binding/hook/snapshot/skip diagnostics surface as in-game toasts. |
| `set_dev_mode` | `HERO_LIB.set_dev_mode(on: boolean)` | safe | Toggle verbose dev surfacing from a script or the Lua console (HERO_LIB.set_dev_mode(true)). One flag, one home; a non-zero number also counts as on. |
| `errors` | `HERO_LIB.errors() -> table[]` | safe | Bounded ring (~64, oldest-first) of recent native BINDING FAULTS, each { kind, where, script, message, time }. Lets a script read its OWN binding faults at runtime (delivers AvaLua Error.hpp's long-standing promise). Independent of dev_mode. |
| `dev_notify` | `HERO_LIB.dev_notify(text: string)` | safe | Push ONE line to the deduped, decaying (~5s), visible diagnostic toast channel — the SAME channel U.log uses when dev_mode is on. Non-string is ignored. |
| `set_combo_status` | `HERO_LIB.set_combo_status(text: string)` | safe | ENGINE-INTERNAL / ADVANCED: publish this tick's 'why the combo is waiting/skipping' reason for the Bind Island (e.g. "waiting (bus)" / "skipped (cooldown)"). Not a toast (no per-tick spam); render-thread reads it for a 0.5s tail. Empty/nil clears. |
| `set_can_kill_indicator` | `HERO_LIB.set_can_kill_indicator(hero_id: integer, slot: integer, indices: integer[])` | safe | ENGINE-INTERNAL / ADVANCED: the can-kill ult-icon signal. Call every tick from an always-on feature's on_tick with the ARRAY of killable enemy ENTRY indices (pawn:get_index()): the ESP renderer draws hero_id's ability-slot icon (the ult) accent-tinted over EACH of those enemies, anchored to its ESP box at the user's dragged box-relative offset. An empty/absent array clears it; the signal expires (~0.3s) so a feature toggled off / death / hero swap clears the badge on its own. Only plain ints cross the thread boundary (thread-safe). |
| `UNITS_TO_METERS` | `.UNITS_TO_METERS: number` | safe | Meters per game unit (~0.0265). Multiply units by this to get meters. |
| `METERS_TO_UNITS` | `.METERS_TO_UNITS: number` | safe | Game units per meter (reciprocal of UNITS_TO_METERS). |
| `ENUM_MV_SIM_TYPE` | `.ENUM_MV_SIM_TYPE: table` | safe | Movement-sim type enum { SIMULATE_MOVEMENT = 0, SIMPLE = 1 } for simulate_movement_for_duration. |
| `ENUM_PPS_INFO_FROM` | `.ENUM_PPS_INFO_FROM: table` | safe | Projectile-info source enum { PROJECTILE = 0, GUN = 1 }. |
| `ENUM_PPS_AIM_TO_POS` | `.ENUM_PPS_AIM_TO_POS: table` | safe | Predict-projectile aim-to enum { PAWN_ORIGIN = 0, LIB_TARGET_POS = 1 }. |

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

### Menu

`table` · tier `safe` — Menu tree entry points (Create/Find/Tab) + style/state.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Create` | `Menu.Create(a: string, b?: string, c?: string, d?: string, e?: string) -> MenuNode` | safe | Build/find a menu path; a hero script's path is auto-re-rooted under Heroes/Hero List/<hero>. |
| `Find` | `Menu.Find(a: string, b?: string, c?: string, d?: string, e?: string, f?: string) -> MenuNode\|nil` | safe |  |
| `Tab` | `Menu.Tab(name: string) -> MenuNode` | safe |  |
| `Style` | `Menu.Style(name?: string) -> Color\|table` | safe | Themed color for a palette name (primary/text/background/shadow + aliases); no arg returns the full theme table. |
| `Opened` | `Menu.Opened() -> boolean` | safe |  |

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
| `FOVToPixelRadius` | `Aim.FOVToPixelRadius(fovDegrees: number) -> number` | safe | Convert an aim FOV in degrees to a screen-pixel radius. |

### callback

`table` · tier `safe` — Event registration objects; register a handler with :set(function).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `on_pre_createmove` | `on_pre_createmove` | safe |  |
| `on_createmove` | `on_createmove` | safe |  |
| `on_frame` | `on_frame` | safe |  |
| `on_draw` | `on_draw` | safe |  |
| `on_add_modifier` | `on_add_modifier` | safe |  |
| `on_remove_modifier` | `on_remove_modifier` | safe |  |
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
| `on_pre_frame` | `on_pre_frame` | safe | Per-frame game-thread work begins (brackets with on_post_frame). |
| `on_post_frame` | `on_post_frame` | safe | Per-frame game-thread work ends. |
| `on_pre_framestage` | `callback.on_pre_framestage(stage: integer)` | safe | Frame stage begins; stage is a FrameStage enum value (only NET_UPDATE_POSTDATAUPDATE_END fires this build). |
| `on_post_framestage` | `callback.on_post_framestage(stage: integer)` | safe | Frame stage ends; stage is a FrameStage enum value. |
| `on_modifier_added` | `on_modifier_added` | safe | Alias of on_add_modifier (same per-script slot). |
| `on_modifier_removed` | `on_modifier_removed` | safe | Alias of on_remove_modifier (same per-script slot). |
| `on_fire_bullets` | `on_fire_bullets` | safe | Alias of on_bullet_create (same per-script slot). |
| `on_key_event` | `callback.on_key_event(code: integer, isDown: boolean) -> boolean\|nil` | safe | Alias of on_key (same per-script slot). Also reports mouse buttons via the standard VK_* code (see on_key) — a truthy return claims the button press exactly like it claims a key. |

### ImGui

`table` · tier `safe` — Immediate-mode GUI primitives.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Begin` | `Begin` | safe |  |
| `End` | `End` | safe |  |
| `Window` | `Window` | safe |  |
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
| `is_pressed` | `Input.is_pressed(vk: integer) -> boolean` | safe |  |
| `cursor_in_bounds` | `cursor_in_bounds` | safe |  |
| `GetMousePos` | `Input.GetMousePos() -> table` | safe | Returns { x, y }. |
| `get_cursor_pos` | `get_cursor_pos` | safe |  |
| `GetMouseDelta` | `GetMouseDelta` | safe |  |
| `mouse_wheel` | `Input.mouse_wheel() -> integer` | safe | Vertical mouse-wheel delta accumulated since the last call (WHEEL_DELTA=120 units; +away from user / -toward). Consumes the accumulator (exchange-to-0) so a per-frame poll never double-counts a notch. |
| `mouse_wheel_h` | `Input.mouse_wheel_h() -> integer` | safe | Horizontal mouse-wheel delta since the last call (shift-scroll / tilt-wheel, WM_MOUSEHWHEEL). Same units/consume semantics as mouse_wheel(). |

### Keys

`table` · tier `safe` — Key-code constants.

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

`table` · tier `safe` — Entity enumeration (local pawn / enemies / allies / by class).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `local_pawn` | `entity_list.local_pawn() -> PlayerPawn\|nil` | safe |  |
| `enemies` | `entity_list.enemies() -> PlayerPawn[]` | safe |  |
| `allies` | `entity_list.allies() -> PlayerPawn[]` | safe |  |
| `by_class_name` | `entity_list.by_class_name(class: string) -> table` | safe |  |
| `by_class_name_any` | `entity_list.by_class_name_any(class: string) -> Entity[]` | safe | Like by_class_name but with NO player-pawn filter: returns generic Entity usertypes for ANY class match (NPCs / structures / projectiles). The ONLY entity_list path to the lane Guardian ("C_NPC_TrooperBoss") and other bosses — by_class_name hard-filters to player pawns, so it can never see one. Walks the raw entity system (a boss NPC is not bucketed in the type cache). |
| `local_controller` | `entity_list.local_controller() -> Entity\|nil` | safe | The local player's controller (GameUtils::GetLocalController), or nil. |
| `players` | `entity_list.players() -> PlayerPawn[]` | safe | Every player hero-pawn (controller->hero-pawn walk + pawn bucket, deduped) — includes PRE-INIT players and controller-less dummies/bots. 1-indexed. |
| `heroes` | `entity_list.heroes() -> PlayerPawn[]` | safe | Identical to entity_list.players (same enumeration). |
| `by_index` | `entity_list.by_index(index: integer) -> PlayerPawn\|nil` | safe | Resolve a 0-based entity ENTRY index to a PlayerPawn (nil if the slot is not a Citadel player pawn). |
| `get_all` | `entity_list.get_all() -> PlayerPawn[]` | safe | Every cached CITADEL_PLAYER_PAWN (pawn bucket only; capped 1024). Prefer entity_list.players for full coverage. |
| `get_all_entities` | `entity_list.get_all_entities() -> Entity[]` | safe | GENERIC walk over EVERY cached entity type as Entity usertypes (identity-checked; capped 4096). |
| `entity_by_index` | `entity_list.entity_by_index(index: integer) -> Entity\|nil` | safe | Resolve ANY 0-based entity index to a generic Entity usertype (not just player pawns), or nil. |
| `by_handle` | `entity_list.by_handle(raw_handle: integer) -> Entity\|nil` | safe | Resolve a RAW CHandle m_Index (entry index + serial bits, serial-validated) to a generic Entity usertype, or nil. This is the value callback.on_particle_create's `index` field carries, and it is also what PlayerPawn:get_handle() and Entity:get_handle() now return — so a get_handle() value round-trips through here correctly. It is NOT a bare entry index: for that use entity_by_index / get_index(). |
| `teammates` | `entity_list.teammates() -> PlayerPawn[]` | safe | Same-team hero-pawns EXCLUDING the local pawn (identical to entity_list.allies). |
| `team_filter` | `.team_filter: table` | safe | Constant team hints: { enemy = 3, ally = 2, all = 0 } — Deadlock TEAM SLOTS, not 0/1/2 array indices. |

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

### convar

`table` · tier `safe` — Source2 ConVar table (convar.<name> -> lua_convar_t).

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
| `save` | `JSON.save(filename: string, t: table, pretty?: boolean) -> boolean` | native | Write table to ScriptData\<name>.json (pretty default TRUE). |
| `load` | `JSON.load(filename: string) -> any` | native | Read+parse ScriptData\<name>.json (nil on missing/parse error). |
| `exists` | `JSON.exists(filename: string) -> boolean` | native | ScriptData\<name>.json exists. |
| `delete` | `JSON.delete(filename: string) -> boolean` | native | Delete ScriptData\<name>.json. |
| `list` | `JSON.list() -> string[]` | native | Array of *.json filenames in ScriptData. |

### Math

`table` · tier `safe` — Extended math helpers.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `GetViewMatrix` | `Math.GetViewMatrix() -> table\|nil` | safe | Current 4x4 view-projection matrix (row-major table). |
| `GetViewport` | `Math.GetViewport() -> table\|nil` | safe | Current viewport { x, y, w, h }. |
| `WorldToScreenMatrix` | `Math.WorldToScreenMatrix(pos: Vector3) -> table\|nil` | safe | World-to-screen using the view matrix; { x, y, visible }. |
| `UNITS_TO_METERS` | `.UNITS_TO_METERS: number` | safe | Authoritative units->meters scale constant. |
| `UNITS_PER_METER` | `.UNITS_PER_METER: number` | safe | Authoritative meters->units scale constant. |
| `UnitsToMeters` | `Math.UnitsToMeters(u: number) -> number` | safe |  |
| `MetersToUnits` | `Math.MetersToUnits(m: number) -> number` | safe |  |
| `Sign` | `Math.Sign(x: number) -> number` | safe | -1 / 0 / 1. |
| `Round` | `Math.Round(x: number, decimals?: integer) -> number` | safe | Round to nearest; optional decimal places. |
| `Approach` | `Math.Approach(current: number, target: number, rate: number, dt: number) -> number` | safe | Frame-rate-aware move toward target (rate = fraction/sec). |
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
| `AnglesToForward` | `Math.AnglesToForward(angles: Angle) -> Vector3` | safe | Angle (or {pitch,yaw} table) -> unit forward vector. |
| `Direction` | `Math.Direction(from: Vector3, to: Vector3) -> Vector3` | safe | Normalized direction from->to (zero if coincident). |
| `WorldToScreen` | `Math.WorldToScreen(worldPos: Vector3) -> table` | safe | Project a world point; returns { x, y, visible }. |
| `Distance` | `Math.Distance(pos1: Vector3, pos2: Vector3) -> number` | safe | 3D distance in METERS (units * UNITS_TO_METERS). |
| `Distance2D` | `Math.Distance2D(pos1: Vector3, pos2: Vector3) -> number` | safe | Horizontal (x,y) distance in METERS; ignores z. |
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
| `GetBarrierHealth` | `Combat.GetBarrierHealth(pawn: PlayerPawn) -> number` | safe | Bonus/barrier health on the pawn. |
| `IsTargetBelowHealth` | `Combat.IsTargetBelowHealth(pawn: PlayerPawn, health_threshold: number) -> boolean` | safe | True if the pawn's health is below the threshold. |
| `RunMouseAimbot` | `Combat.RunMouseAimbot(target_pos: Vector3, speed?: number, deadzone?: number, max_per_frame?: number) -> boolean` | native | Drive the REAL hardware mouse toward target_pos. |
| `RunFastMouseAimbot` | `Combat.RunFastMouseAimbot(target_pos: Vector3) -> boolean` | native | Snap the REAL hardware mouse toward target_pos (fast path). |
| `GetAngleDiffToTarget` | `Combat.GetAngleDiffToTarget(eye_pos: Vector3, target_pos: Vector3, view_pitch: number, view_yaw: number) -> number` | safe | Angular error (degrees) between the view and the direction to target_pos. |
| `IsGameFocused` | `Combat.IsGameFocused() -> boolean` | safe | True when the game window has focus. |
| `ShouldRunFeatures` | `Combat.ShouldRunFeatures() -> boolean` | safe | True only when features may act: cheat menu CLOSED, game in play mode, AND window foregrounded. Stronger than IsGameFocused (which is just the window). Reactive features (auto-parry) should gate on this so they don't act while the menu/cursor is up. |

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
| `get_camera_angles` | `utils.get_camera_angles() -> Angle` | safe | Live VIEW angles (the source the C++ aimbot reads). READ-ONLY. (0,0,0) if the input singleton is unavailable. |
| `set_camera_angles` | `utils.set_camera_angles(angles: Angle)` | safe | INTENTIONAL NO-OP: scripts must never write view/camera angles (aim spoofs camera POSITION only). Kept so callers don't nil-index. |
| `get_camera_pos` | `utils.get_camera_pos() -> Vector3` | safe | Live EYE position, camera-spoof aware (usercmd vec_camera_position when a PSilent spoof is armed, else pawn eye). Zero only when no local pawn. |
| `calc_angle` | `utils.calc_angle(from: Vector3, to: Vector3) -> Angle` | safe | Euler angle pointing from `from` to `to`. |
| `distance` | `utils.distance(a: Vector3, b: Vector3) -> number` | safe | 3D distance in game UNITS. |
| `distance_2d` | `utils.distance_2d(a: Vector3, b: Vector3) -> number` | safe | 2D (XY) distance in game UNITS. |
| `get_game_time` | `utils.get_game_time() -> number` | safe | Current game time (m_flCurrentTime), seconds; 0 when unavailable. |
| `world_to_screen` | `utils.world_to_screen(world_pos: Vector3) -> table\|nil` | safe | { x, y, visible = true } screen coords, or nil when off-screen / behind camera. |
| `normalize_angle` | `utils.normalize_angle(angle: number) -> number` | safe | Wrap a degree angle into [-180, 180]. |
| `angle_diff` | `utils.angle_diff(a: number, b: number) -> number` | safe | Shortest signed difference a-b in degrees, wrapped to [-180, 180]. |
| `lerp` | `utils.lerp(a: number, b: number, t: number) -> number` | safe | Linear interpolation a + (b-a)*t (t not clamped). |
| `clamp` | `utils.clamp(value: number, min: number, max: number) -> number` | safe | Clamp value to [min, max]. |
| `execute_command` | `utils.execute_command(command: string) -> boolean` | safe | Run a client console command via IVEngineToClient::ExecuteClientCmd (e.g. "play <sound>"). COMMAND execution only, never a ConVar write. SEH-guarded; returns false (never throws) on an empty command, an unresolved engine interface, or a caught native fault. |

### draw

`namespace` · tier `safe` — Legacy 2D/3D draw helpers (render-stack; render-context only). Colors are POSITIONAL {r,g,b,a} arrays (indices 1..4), NOT named {r=,g=,b=} tables.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `text` | `draw.text(x: number, y: number, text: string, color?: table)` | safe | Center-anchored string via the render stack. color = {r,g,b,a} array (indices 1..4). |
| `line` | `draw.line(x1: number, y1: number, x2: number, y2: number, color?: table, thickness?: number)` | safe | 2D line. color = {r,g,b,a} array; thickness default 1. |
| `rect` | `draw.rect(x: number, y: number, w: number, h: number, color?: table, filled?: boolean, rounding?: number)` | safe | Rect at (x,y) size (w,h). rounding is accepted but IGNORED. |
| `circle` | `draw.circle(x: number, y: number, radius: number, color?: table, filled?: boolean)` | safe | 2D circle (radius in PIXELS). |
| `line_3d` | `draw.line_3d(x1: number, y1: number, z1: number, x2: number, y2: number, z2: number, color?: table, thickness?: number)` | safe | World-space line between two points (6 scalars). |
| `circle_3d` | `draw.circle_3d(x: number, y: number, z: number, radius: number, color?: table)` | safe | World-space circle at (x,y,z), radius in game UNITS. |

### global_vars

`table` · tier `safe` — CGlobalVarsBase timing/frame accessors (raw clock; plausible fallbacks when globals are null).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `curtime` | `global_vars.curtime() -> number` | safe | m_flCurrentTimeRaw (RAW clock; 0.0 if globals null). |
| `latency_incoming` | `global_vars.latency_incoming() -> number` | safe | Local network latency in SECONDS (same source as net_channel.get_latency; a true in/out split awaits the CNetChan flow RE). 0.0 when not connected. |
| `latency_outgoing` | `global_vars.latency_outgoing() -> number` | safe | Local network latency in SECONDS (see latency_incoming). 0.0 when not connected. |
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

`namespace` · tier `native` — Sandboxed file I/O (rooted at %APPDATA%\Avalanche\ScriptFiles). TRUSTED/local.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `open` | `io.open(filename: string, mode?: string) -> File?` | native | Open a file (mode default "r"); File handle \| nil. RELATIVE paths are sandboxed under %APPDATA%\Avalanche\ScriptFiles; ABSOLUTE paths are honored as-is (io is trusted-only, so this is the authorized absolute-path access for trusted/local scripts — Steam vdf/avatarcache reads, assets next to the script, config import/export). |
| `exists` | `io.exists(filename: string) -> boolean` | native | Sandboxed path exists. |
| `remove` | `io.remove(filename: string) -> boolean` | native | Delete a sandboxed file. |
| `rename` | `io.rename(oldname: string, newname: string) -> boolean` | native | Rename within the sandbox (false on failure). |
| `lines` | `io.lines(filename: string) -> string[]` | native | 1-indexed array of the file's lines (empty if unopenable). |

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
| `IN_MOVELEFT` | `.IN_MOVELEFT: integer` | safe | 0x200 |
| `IN_MOVERIGHT` | `.IN_MOVERIGHT: integer` | safe | 0x400 |
| `IN_ATTACK2` | `.IN_ATTACK2: integer` | safe | 0x800 (secondary fire / zoom-ADS; NOT melee) |
| `IN_RELOAD` | `.IN_RELOAD: integer` | safe | 0x2000 |
| `IN_SPEED` | `.IN_SPEED: integer` | safe | 0x10000 |
| `IN_ZOOM` | `.IN_ZOOM: integer` | safe | 0x80000 |
| `IN_WEAPON1` | `.IN_WEAPON1: integer` | safe | 0x100000000 |
| `IN_WEAPON2` | `.IN_WEAPON2: integer` | safe | 0x100000000 (ALIAS of IN_WEAPON1) |
| `IN_GRENADE1` | `.IN_GRENADE1: integer` | safe | 0x0 (no CUserCmd bit — pressing does nothing) |
| `IN_GRENADE2` | `.IN_GRENADE2: integer` | safe | 0x0 (no CUserCmd bit — pressing does nothing) |
| `IN_ABILITY1` | `.IN_ABILITY1: integer` | safe | 0x200000000 |
| `IN_ABILITY2` | `.IN_ABILITY2: integer` | safe | 0x400000000 |
| `IN_ABILITY3` | `.IN_ABILITY3: integer` | safe | 0x800000000 |
| `IN_ABILITY4` | `.IN_ABILITY4: integer` | safe | 0x1000000000 |
| `IN_ITEM1` | `.IN_ITEM1: integer` | safe | 0x2000000000 |
| `IN_ITEM2` | `.IN_ITEM2: integer` | safe | 0x4000000000 |
| `IN_ITEM3` | `.IN_ITEM3: integer` | safe | 0x8000000000 |
| `IN_ITEM4` | `.IN_ITEM4: integer` | safe | 0x10000000000 |
| `IN_ABILITY_HELD` | `.IN_ABILITY_HELD: integer` | safe | 0x40000000000 |
| `IN_INNATE_1` | `.IN_INNATE_1: integer` | safe | 0x100000000000 (wall-dash) |
| `IN_INNATE_2` | `.IN_INNATE_2: integer` | safe | 0x200000000000 |
| `IN_INNATE_3` | `.IN_INNATE_3: integer` | safe | 0x400000000000 |
| `IN_MANTLE` | `.IN_MANTLE: integer` | safe | 0x1000000000000 |
| `IN_ALT_CAST` | `.IN_ALT_CAST: integer` | safe | 0x20000000000000 (self-cast) |
| `IN_ZIPLINE` | `.IN_ZIPLINE: integer` | safe | 0x100000000000000 |
| `IN_CANCEL_ABILITY` | `.IN_CANCEL_ABILITY: integer` | safe | 0x1000000000000000 (detonate/release) |

### Enum.ButtonCode

`table` · tier `safe` — Source2 ButtonCode key ordinals (MenuNode:Bind default-key seeds).

| Member | Signature | Tier | Description |
|---|---|---|---|
| `KEY_NONE` | `.KEY_NONE: integer` | safe | -1 |
| `KEY_0` | `.KEY_0: integer` | safe | 0 |
| `KEY_1` | `.KEY_1: integer` | safe | 1 |
| `KEY_2` | `.KEY_2: integer` | safe | 2 |
| `KEY_3` | `.KEY_3: integer` | safe | 3 |
| `KEY_4` | `.KEY_4: integer` | safe | 4 |
| `KEY_5` | `.KEY_5: integer` | safe | 5 |
| `KEY_6` | `.KEY_6: integer` | safe | 6 |
| `KEY_7` | `.KEY_7: integer` | safe | 7 |
| `KEY_8` | `.KEY_8: integer` | safe | 8 |
| `KEY_9` | `.KEY_9: integer` | safe | 9 |
| `KEY_A` | `.KEY_A: integer` | safe | 10 |
| `KEY_B` | `.KEY_B: integer` | safe | 11 |
| `KEY_C` | `.KEY_C: integer` | safe | 12 |
| `KEY_D` | `.KEY_D: integer` | safe | 13 |
| `KEY_E` | `.KEY_E: integer` | safe | 14 |
| `KEY_F` | `.KEY_F: integer` | safe | 15 |
| `KEY_G` | `.KEY_G: integer` | safe | 16 |
| `KEY_H` | `.KEY_H: integer` | safe | 17 |
| `KEY_I` | `.KEY_I: integer` | safe | 18 |
| `KEY_J` | `.KEY_J: integer` | safe | 19 |
| `KEY_K` | `.KEY_K: integer` | safe | 20 |
| `KEY_L` | `.KEY_L: integer` | safe | 21 |
| `KEY_M` | `.KEY_M: integer` | safe | 22 |
| `KEY_N` | `.KEY_N: integer` | safe | 23 |
| `KEY_O` | `.KEY_O: integer` | safe | 24 |
| `KEY_P` | `.KEY_P: integer` | safe | 25 |
| `KEY_Q` | `.KEY_Q: integer` | safe | 26 |
| `KEY_R` | `.KEY_R: integer` | safe | 27 |
| `KEY_S` | `.KEY_S: integer` | safe | 28 |
| `KEY_T` | `.KEY_T: integer` | safe | 29 |
| `KEY_U` | `.KEY_U: integer` | safe | 30 |
| `KEY_V` | `.KEY_V: integer` | safe | 31 |
| `KEY_W` | `.KEY_W: integer` | safe | 32 |
| `KEY_X` | `.KEY_X: integer` | safe | 33 |
| `KEY_Y` | `.KEY_Y: integer` | safe | 34 |
| `KEY_Z` | `.KEY_Z: integer` | safe | 35 |
| `KEY_SPACE` | `.KEY_SPACE: integer` | safe | 64 |
| `KEY_ENTER` | `.KEY_ENTER: integer` | safe | 63 |
| `KEY_ESCAPE` | `.KEY_ESCAPE: integer` | safe | 69 |
| `KEY_TAB` | `.KEY_TAB: integer` | safe | 66 |
| `KEY_BACKSPACE` | `.KEY_BACKSPACE: integer` | safe | 65 |
| `KEY_LSHIFT` | `.KEY_LSHIFT: integer` | safe | 78 |
| `KEY_RSHIFT` | `.KEY_RSHIFT: integer` | safe | 79 |
| `KEY_LCONTROL` | `.KEY_LCONTROL: integer` | safe | 82 |
| `KEY_RCONTROL` | `.KEY_RCONTROL: integer` | safe | 83 |
| `KEY_LALT` | `.KEY_LALT: integer` | safe | 80 |
| `KEY_RALT` | `.KEY_RALT: integer` | safe | 81 |
| `KEY_F1` | `.KEY_F1: integer` | safe | 91 |
| `KEY_F2` | `.KEY_F2: integer` | safe | 92 |
| `KEY_F3` | `.KEY_F3: integer` | safe | 93 |
| `KEY_F4` | `.KEY_F4: integer` | safe | 94 |
| `KEY_F5` | `.KEY_F5: integer` | safe | 95 |
| `KEY_F6` | `.KEY_F6: integer` | safe | 96 |
| `KEY_F7` | `.KEY_F7: integer` | safe | 97 |
| `KEY_F8` | `.KEY_F8: integer` | safe | 98 |
| `KEY_F9` | `.KEY_F9: integer` | safe | 99 |
| `KEY_F10` | `.KEY_F10: integer` | safe | 100 |
| `KEY_F11` | `.KEY_F11: integer` | safe | 101 |
| `KEY_F12` | `.KEY_F12: integer` | safe | 102 |

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

### WeaponBulletData

`usertype` · tier `safe` — Local weapon bullet physics returned by Aim.GetBulletPhysics.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Speed` | `.Speed: number` | safe | Bullet speed (game units/sec). |
| `Gravity` | `.Gravity: number` | safe | Bullet gravity scalar. |
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
| `set_timeout` | `set_timeout(callback: function, seconds: number) -> integer` | safe |  |
| `set_interval` | `set_interval(callback: function, seconds: number) -> integer` | safe |  |
| `clear_timeout` | `clear_timeout(handle: integer) -> boolean` | safe |  |
| `clear_interval` | `clear_interval(handle: integer) -> boolean` | safe |  |
| `has_capability` | `has_capability(name: string) -> boolean` | safe |  |
| `set_thread_safe_reads` | `set_thread_safe_reads(enabled: boolean)` | safe | Per-script opt-out of snapshot-routed entity reads. Default true (SAFE): render-thread entity scalar reads come from an immutable per-tick snapshot. false => LIVE reads on the render thread too (author owns the thread-affinity risk). |
| `execute_after` | `execute_after(delay: number, fn: function) -> integer\|nil` | safe | Deferred game-thread call (alias of common.execute_after). |
| `raw_struct` | `raw_struct(address: integer, class?: string) -> raw_struct` | native | Construct a typed view over a native struct pointer (optional schema class name for by-name field access). |
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
| `on_render` | `on_render()` | safe |  |
| `on_entity_created` | `on_entity_created(entity: Entity, idx: integer)` | safe |  |
| `on_entity_deleted` | `on_entity_deleted(entity: Entity\|nil, idx: integer)` | safe |  |
| `on_modifier_added` | `on_modifier_added(mod: Modifier, owner: PlayerPawn)` | safe |  |
| `on_modifier_removed` | `on_modifier_removed(mod: Modifier, owner: PlayerPawn)` | safe |  |
| `on_fire_bullets` | `on_fire_bullets(ctx: any)` | safe |  |
| `on_take_damage` | `on_take_damage(ev: any, name: string)` | safe |  |
| `on_particle_create` | `on_particle_create(ctx: any)` | safe |  |
| `on_game_event` | `on_game_event(ev: GameEvent, name: string)` | safe |  |
| `on_user_message` | `on_user_message(id: integer, bytes: string) -> boolean` | safe |  |
| `on_net_message` | `on_net_message(id: integer, bytes: string) -> boolean` | safe |  |
| `on_draw` | `on_draw()` | safe | Primary render callback — fires every frame on the RENDER thread. Do 2D/3D drawing (Render / ImGui / Aim world-to-screen) here, not game-thread entity reads. |
| `on_pre_createmove` | `on_pre_createmove(cmd: UserCmd)` | safe | Game thread. Runs just BEFORE on_createmove on the same per-tick UserCmd — for logic that must precede the main movement/aim handler. |
| `on_add_modifier` | `on_add_modifier(mod: Modifier, owner: PlayerPawn)` | safe | Game thread. A modifier (buff/debuff) was added to an entity. Alias of on_modifier_added (same handler slot). |
| `on_remove_modifier` | `on_remove_modifier(mod: Modifier, owner: PlayerPawn)` | safe | Game thread. Fires just BEFORE the engine frees a modifier — read it now, do NOT retain the pointer. Alias of on_modifier_removed (same handler slot). |
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

## Compatibility aliases

Legacy names kept working; prefer the canonical API above.

| Member | Signature | Tier | Description |
|---|---|---|---|
| `Vector` | `.Vector: Vector3` | safe | Alias of Vector3 (LuaEntityAPI.cpp:186). |
| `ImColor` | `.ImColor: Color` | safe | Alias of Color (LuaRenderAPI ImColor constructor). |
| `TargetSelection` | `.TargetSelection: lua_target_selection_wrapper_t` | safe | Factory alias of lua_target_selection_wrapper_t (LuaUsertypes.cpp:1981). |

---

_Generated from `src/data/lua_api.json`. Regenerate with `npm run gen-lua-api`._
