# sngrep: review of 69 open issues (2026-10-13)

**Scope**: All **69 currently open issue threads** in `irontec/sngrep` (excludes pull requests). This is **contributor triage**: no official upstream labels or state changes are implied.

## Notes on access and scope

- Connected GitHub integration can write to `darwvin-dev/sngrep` but returned **403 Forbidden** on posting a comment or opening a PR in upstream `irontec/sngrep`. Upstream labels/assignments/closures were **not** changed.
- Open issues may already have a fix in HEAD; only reproduced problems can be called confirmed outstanding bugs. Historical reports are not proof of current regressions.
- Priority ranks are engineering triage judgments, **not maintainer priorities**. P1: impact/urgency or reviewer attention. P3: aged platform/docs/low-current-applicability. All descriptions should be verified against current code before merging.
- Existing upstream PRs: #564 (issue #275), #582 (#503), #583 (#501), #584 (#435). Media Inspector PRs #579, #580, #581 cover parts of issues #285/#412, but not necessarily the entire request.
- New contributor fork draft PRs: [CSV export #7](https://github.com/darwvin-dev/sngrep/pull/7) for issue #265; [Git SHA in version #8](https://github.com/darwvin-dev/sngrep/pull/8) for #333.
- Do **not** mass-comment or close issues without tested resolutions.

## Item-by-item recommended disposition

| Issue | Original title | Category | Rank | Proposed label | Proposed disposition | Specific next action |
|---|---|---|---|---|---|---|
| [#79](https://github.com/irontec/sngrep/issues/79) | openbsd warnings during compiling | Build / packages / platforms | P3 | enhancement | Design / maintainer decision | Verify current OpenBSD warnings; replace unsafe formatting only with tests |
| [#81](https://github.com/irontec/sngrep/issues/81) | FTBFS on hppa/parisc architecture | Build / packages / platforms | P3 | enhancement | Design / maintainer decision | Reproduce test keyboard tables under big-endian emulator, then fix byte encoding |
| [#102](https://github.com/irontec/sngrep/issues/102) | SIP TCP Retrans issue at flow viewer | Parsing / SIP / TCP | P1 | needs-repro | Reproduce + regression | Build PCAP regression for retransmitted TCP bytes vs SIP messages |
| [#115](https://github.com/irontec/sngrep/issues/115) | don'nt show rtp flow arrow when one leg with DMZ and sdp address with DMZ public address | RTP / RTCP / media | P2 | needs-repro | Reproduce + regression | Test RTP mapping through translated DMZ SDP addresses with a PCAP |
| [#146](https://github.com/irontec/sngrep/issues/146) | Showing RTP stream when there is NAT | RTP / RTCP / media | P2 | needs-repro | Reproduce + regression | Add NAT RTP/SDP mapping fixture; assess RTP flow association |
| [#156](https://github.com/irontec/sngrep/issues/156) | Add support for not fully RFC compliant SIP messages | Parsing / SIP / TCP | P2 | needs-repro | Reproduce + regression | Fuzz malformed SIP fixtures and define permissive parser boundaries |
| [#166](https://github.com/irontec/sngrep/issues/166) | Feature Request: Export to Cloudshark | Export / documentation / metadata | P3 | enhancement | Design / maintainer decision | Check CloudShark API, authentication and redaction requirements before integration |
| [#167](https://github.com/irontec/sngrep/issues/167) | Feature Request: Display custom headers in list format | UI / callflow | P2 | enhancement | Design / maintainer decision | Design column configuration for arbitrary SIP header names; sanitize length |
| [#180](https://github.com/irontec/sngrep/issues/180) | Display RE-INVITE in callflow | UI / callflow | P2 | enhancement | Design / maintainer decision | Differentiate in-dialog re-INVITE from initial INVITE using dialog state |
| [#182](https://github.com/irontec/sngrep/issues/182) | Feature Request: Ability to group SIP server IP addresses | UI / callflow | P2 | enhancement | Design / maintainer decision | Group multiple configured IPs into a logical server in callflow |
| [#196](https://github.com/irontec/sngrep/issues/196) | Allow set capture device to none | Capture / packet I-O | P2 | question | Answer / documentation | Provide explicit HEP-only mode without raw-interface capture |
| [#204](https://github.com/irontec/sngrep/issues/204) | hide duplicate packets on VRRP | UI / callflow | P2 | needs-repro | Reproduce + regression | Deduplicate TCP/UDP frames safely without removing valid SIP retransmissions |
| [#210](https://github.com/irontec/sngrep/issues/210) | horizontal scrolling in call view | UI / callflow | P2 | enhancement | Design / maintainer decision | Support horizontal scrolling for many call-flow legs |
| [#211](https://github.com/irontec/sngrep/issues/211) | non-ascii symbols can cause display issue | UI / callflow | P2 | needs-repro | Reproduce + regression | Reproduce multibyte input terminal-width rendering and fix cell count |
| [#220](https://github.com/irontec/sngrep/issues/220) | sngrep F2 save TLS issue  | TLS / HEP / encrypted | P2 | needs-repro | Reproduce + regression | Investigate TLS save/reopen missing handshake, with encrypted PCAP fixture |
| [#221](https://github.com/irontec/sngrep/issues/221) | Don'nt show TLS callflow with some scenarios | TLS / HEP / encrypted | P2 | needs-repro | Reproduce + regression | Reproduce TLS startup-mid-session and decryption state |
| [#224](https://github.com/irontec/sngrep/issues/224) | sngreprc man page | Build / packages / platforms | P3 | enhancement | Design / maintainer decision | Write a source-controlled sngreprc man page with sync check |
| [#240](https://github.com/irontec/sngrep/issues/240) | segfault if header is longer than 128 byte | Crash / memory / resource use | P1 | enhancement | Design / maintainer decision | Maintainer mentioned an earlier fix; verify current head and add crash regression before closing |
| [#242](https://github.com/irontec/sngrep/issues/242) | Static compilation and linking | Build / packages / platforms | P3 | enhancement | Design / maintainer decision | Test static linker dependency closure on Linux release build |
| [#244](https://github.com/irontec/sngrep/issues/244) | Group up sip calls | UI / callflow | P2 | enhancement | Design / maintainer decision | Share design with #182/#504; preserve ports and distinct physical peers |
| [#245](https://github.com/irontec/sngrep/issues/245) | support for GRE protocol | Capture / packet I-O | P2 | needs-repro | Reproduce + regression | Check GRE encapsulated SIP PCAP and support via link decoder |
| [#246](https://github.com/irontec/sngrep/issues/246) | sngrep localhost centos lost packets | Capture / packet I-O | P2 | needs-repro | Reproduce + regression | Reproduce loopback capture loss on supported OS/kernel, investigate capture type |
| [#250](https://github.com/irontec/sngrep/issues/250) | IPV6 Display problem | UI / callflow | P2 | needs-repro | Reproduce + regression | Fix IPv6 address display width with terminal-size tests |
| [#254](https://github.com/irontec/sngrep/issues/254) | Support for MRCPv2 RFC 6787 | New protocol support | P3 | enhancement | Design / maintainer decision | Ask maintainer whether MRCP belongs in SIP-focused scope before implementation |
| [#255](https://github.com/irontec/sngrep/issues/255) | IPv6 and TLS | TLS / HEP / encrypted | P2 | needs-repro | Reproduce + regression | Reproduce IPv6/TLS capture with key material and PCAP |
| [#259](https://github.com/irontec/sngrep/issues/259) | Same Idx for calls with different call-id | Parsing / SIP / TCP | P2 | needs-repro | Reproduce + regression | Reproduce Call-ID index collision; clarify UI index semantics |
| [#265](https://github.com/irontec/sngrep/issues/265) | Feature Request: Export the entries from the Call List Window to a (.csv) file | Export / documentation / metadata | P2 | in-progress | Contributor PR #7 | Implementation in contributor fork PR #7; manual UI review still needed |
| [#275](https://github.com/irontec/sngrep/issues/275) | SNGREP does not recognize SIP on my Vlan over Vlan QinQ captures - any solution? | Capture / packet I-O | P1 | in-progress | Upstream PR #564 | Upstream PR #564 already open; review/tests before any new changes |
| [#280](https://github.com/irontec/sngrep/issues/280) | TLS different behavior | TLS / HEP / encrypted | P2 | needs-repro | Reproduce + regression | Reproduce TLS cipher/client contrast on current build; old 1.4.5 report |
| [#285](https://github.com/irontec/sngrep/issues/285) | Feature Request: RTCP analysis | RTP / RTCP / media | P1 | enhancement | Design / maintainer decision | RTCP report parsing still needs explicit scope; #579-581 cover some RTP inspection |
| [#289](https://github.com/irontec/sngrep/issues/289) | Adding port to be analysed as SIP | Parsing / SIP / TCP | P2 | question | Answer / documentation | Comments identify IPv6 fragmented UDP; avoid restrictive BPF port filters and request PCAP |
| [#315](https://github.com/irontec/sngrep/issues/315) | Asterisk PJSIP + HEP | TLS / HEP / encrypted | P3 | question | Answer / documentation | Support question: explain Asterisk HEP settings and what sngrep can actually receive |
| [#320](https://github.com/irontec/sngrep/issues/320) | Add Support for T.38 streams | RTP / RTCP / media | P2 | needs-repro | Reproduce + regression | Use attached T.38 PCAP to verify UDPTL media export after re-INVITE |
| [#321](https://github.com/irontec/sngrep/issues/321) | Feature-Request: Add support for IPv6 assembly | Parsing / SIP / TCP | P2 | needs-repro | Reproduce + regression | Regression test IPv6 fragmented 200 OK from attached trace |
| [#323](https://github.com/irontec/sngrep/issues/323) | Multiple Input Files and No Documentation on Sorting | Capture / packet I-O | P1 | needs-repro | Reproduce + regression | Make multi-PCAP offline input globally time-ordered, with interleaving fixture |
| [#331](https://github.com/irontec/sngrep/issues/331) | feature: show media streams when mixed IPv4 and IPv6 for media and signaling | RTP / RTCP / media | P2 | needs-repro | Reproduce + regression | Preserve media streams with mixed IPv4/IPv6 signaling; fixture provided |
| [#333](https://github.com/irontec/sngrep/issues/333) | feature: output of commit id in version output | Export / documentation / metadata | P2 | in-progress | Contributor PR #8 | Implementation in contributor fork PR #8; CI validation pending |
| [#337](https://github.com/irontec/sngrep/issues/337) | Crash on MacOS Catalina | Crash / memory / resource use | P3 | needs-repro | Reproduce + regression | Old Catalina-only crash; reproduce on supported macOS before code changes |
| [#339](https://github.com/irontec/sngrep/issues/339) | Feature-Request: Support for multiple X-Call-ID headers | Parsing / SIP / TCP | P2 | enhancement | Design / maintainer decision | Support multiple X-Call-ID values in extended grouping without loops |
| [#364](https://github.com/irontec/sngrep/issues/364) | session key file and pcapng format support | TLS / HEP / encrypted | P1 | enhancement | Design / maintainer decision | Security review for TLS secrets, pcapng key blocks and redaction |
| [#395](https://github.com/irontec/sngrep/issues/395) | illegal hardware instruction when read pcap | Crash / memory / resource use | P1 | needs-repro | Reproduce + regression | Collect failing PCAP/build/CPU diagnostics to reproduce illegal instruction |
| [#408](https://github.com/irontec/sngrep/issues/408) | SIP messages out-of-order in Call Flow | Parsing / SIP / TCP | P1 | needs-repro | Reproduce + regression | Timestamp-sort callflow after multi-source packets; add deterministic fixture |
| [#412](https://github.com/irontec/sngrep/issues/412) | RTP Analysis | RTP / RTCP / media | P1 | enhancement | Design / maintainer decision | Coordinate with #579-581; add RTCP validation/jitter/loss correctness tests |
| [#426](https://github.com/irontec/sngrep/issues/426) | Cannot allocate memory | Capture / packet I-O | P1 | needs-repro | Reproduce + regression | Investigate Linux RX_RING resource allocation, limits and fallback path |
| [#428](https://github.com/irontec/sngrep/issues/428) | patch to deduplicate HEP encapsulated packets coming from multiple proxies/agents | TLS / HEP / encrypted | P1 | needs-repro | Reproduce + regression | HEP dedup by stable identity/timestamp with time-bounded cache, false-positive tests |
| [#429](https://github.com/irontec/sngrep/issues/429) | [FEATURE REQUEST] limit number of transactions in dialogs | Crash / memory / resource use | P1 | needs-repro | Reproduce + regression | Bound REGISTER/SUBSCRIBE transactions without destroying active call context |
| [#433](https://github.com/irontec/sngrep/issues/433) | Feature Request: Start sngrep with no listening interface (HEP only) | Capture / packet I-O | P2 | question | Answer / documentation | Validate -L HEP-only mode does not activate interface; related to #196 |
| [#435](https://github.com/irontec/sngrep/issues/435) | Question: Is there a way to theme sngrep? | UI / callflow | P2 | in-progress | Upstream PR #584 | Theme implementation proposed in upstream PR #584; wait for review |
| [#439](https://github.com/irontec/sngrep/issues/439) | Capturing SIPS + RTP/SAVP with asterisk  | TLS / HEP / encrypted | P2 | question | Answer / documentation | Explain HEP SIP capture vs RTP media export limits; verify Asterisk producer payload |
| [#441](https://github.com/irontec/sngrep/issues/441) | Arch aur out of date | Build / packages / platforms | P3 | question | Answer / documentation | AUR is maintained separately; confirm current AUR version and coordinate with packager |
| [#447](https://github.com/irontec/sngrep/issues/447) | TLS capture using eBpf | TLS / HEP / encrypted | P2 | enhancement | Design / maintainer decision | Assess eBPF SSL capture feasibility, privilege model and key security with maintainer |
| [#457](https://github.com/irontec/sngrep/issues/457) | Steps for PgUp/PgDown 4 - Other values show no effect | UI / callflow | P2 | needs-repro | Reproduce + regression | Verify PgUp/PgDown step setting for both views; add keybinding test |
| [#463](https://github.com/irontec/sngrep/issues/463) | enhancement Identity Header | Export / documentation / metadata | P2 | enhancement | Design / maintainer decision | Scope read-only Identity JWT decoding; avoid presenting decoded JWT as verified |
| [#465](https://github.com/irontec/sngrep/issues/465) | SNGREP to capture SIP packets based on file size  | Capture / packet I-O | P2 | enhancement | Design / maintainer decision | Clarify rotate-by-size semantics and interaction with -O packet dump |
| [#466](https://github.com/irontec/sngrep/issues/466) | Problems with Multiple SIP Packets in a TCP Stream | Parsing / SIP / TCP | P1 | needs-repro | Reproduce + regression | Highest-impact TCP framing issue: multiple SIP messages in one stream; incremental parser tests |
| [#467](https://github.com/irontec/sngrep/issues/467) | Display filter search stops working after a while (cannot type or delete multiple characters) | UI / callflow | P1 | needs-repro | Reproduce + regression | Stress-test filter input at 27k dialogs; investigate input-event starvation |
| [#477](https://github.com/irontec/sngrep/issues/477) | documentation on combining multople call flows | Export / documentation / metadata | P3 | question | Answer / documentation | Maintainer already explained: select dialogs with Space then Enter to combine |
| [#486](https://github.com/irontec/sngrep/issues/486) | How Not to capture RTP packets in SNGREP | Capture / packet I-O | P2 | question | Answer / documentation | Do not pass -r to avoid RTP capture; use BPF `not host ... and not port ...` to exclude flows |
| [#489](https://github.com/irontec/sngrep/issues/489) |  can we run sngrep in solaris server ? | Build / packages / platforms | P3 | question | Answer / documentation | Verify Solaris build/runtime on supported target and available libpcap/ncurses |
| [#490](https://github.com/irontec/sngrep/issues/490) | Feature-request: RFC4571 Support  (RTP over TCP) | RTP / RTCP / media | P2 | needs-repro | Reproduce + regression | RFC4571 requires RTP/TCP framing and stream reassembly; design scope first |
| [#495](https://github.com/irontec/sngrep/issues/495) | Sngrep in Different TERM Environments | UI / callflow | P2 | needs-repro | Reproduce + regression | Normalize terminal escape sequences; reproduce PuTTY/TERM details |
| [#496](https://github.com/irontec/sngrep/issues/496) | Open PCAP and Listen to UDP Port | Capture / packet I-O | P2 | enhancement | Design / maintainer decision | Offline PCAP and live HEP combined requires source lifecycle redesign |
| [#499](https://github.com/irontec/sngrep/issues/499) | SNGREP not capturing Fragmented packets | Parsing / SIP / TCP | P1 | needs-repro | Reproduce + regression | Upstream maintainer could not establish missing packet in supplied PCAP; isolate expected fragment |
| [#501](https://github.com/irontec/sngrep/issues/501) | Feature-Request: Add TCP support for HEP3 listen | TLS / HEP / encrypted | P1 | in-progress | Upstream PR #583 | Upstream PR #583 already open; TCP/Hep3 review and CI needed |
| [#503](https://github.com/irontec/sngrep/issues/503) | Add Codec Column to main interface | UI / callflow | P1 | in-progress | Upstream PR #582 | Upstream PR #582 already open; codec negotiation tests and maintainer review needed |
| [#504](https://github.com/irontec/sngrep/issues/504) | To Merge Two IP in single column | UI / callflow | P2 | enhancement | Design / maintainer decision | Same IP grouping topic as #182/#244; confirm how to preserve distinct legs |
| [#505](https://github.com/irontec/sngrep/issues/505) | capture device "any" displays duplicate traffic when bond is configured | Capture / packet I-O | P1 | needs-repro | Reproduce + regression | Identify bond-master/slave duplicates in Linux any captures; design safe opt-in dedup |
| [#510](https://github.com/irontec/sngrep/issues/510) | Feature Request: SCTP Support | Capture / packet I-O | P2 | enhancement | Design / maintainer decision | Confirm if SCTP SIP Signaling belongs in scope; needs transport reassembly |
| [#537](https://github.com/irontec/sngrep/issues/537) | HEP proto saved incorrectly in mixed traffic | Capture / packet I-O | P1 | needs-repro | Reproduce + regression | Recent reproducible HEP + non-HEP mixed PCAP save regression; separate synthetic/raw link type |

## Cross-issue work that should be designed together

- **Group callflow peers**: #182 / #244 / #504. One shared design may cover all three without merging the issue histories.
- **NAT media**: #115 / #146 / #331. Need a common RTP/SDP fixture set; don't assume capture vantage matches the negotiated endpoint address.
- **HEP-only operation**: #196 / #433. Ensure no raw-interface capture on `-L`-only runs and preserve explicit capture-device choice.
- **RTP analysis**: #285 / #412. Read existing upstream stacked #579-581 first, then cover remaining RTCP/RTP metrics.
- **TCP reconstruction**: #102 / #466 / #499. Sequence, framing and IP fragmentation are distinct layers and require distinct regression cases.

## Ready-to-use technical issue responses (NOT posted upstream)

- **#477**: The upstream maintainer already answered: in Call List, press **Space** on each dialog to select multiple calls, then **Enter** to view the combined flow. Do not repeat the same answer as a new comment.
- **#486**: In current CLI, `-r` **enables** RTP capture, so omit `-r` to keep the normal SIP-focused view. To exclude specific flows in libpcap, use a BPF expression such as `not host 192.0.2.10 and not port 9840`. Check `capture.rtp` in config if RTP is still enabled. This does not guarantee zero CPU cost for packets filtered at later stages.
- **#289**: The follow-up says the missing packet is a **fragmented IPv6 UDP INVITE** rather than simply SIP on a non-standard port. The maintainer notes that filters matching TCP/UDP ports can drop non-initial IP fragments before sngrep sees them. Test with an unfiltered PCAP and compare with Wireshark, then provide exact frame numbers.
- **#275**: Upstream PR [#564](https://github.com/irontec/sngrep/pull/564) already handles nested VLAN parsing. Keep this issue open until that change is reviewed and tests pass; VXLAN concerns from discussion are not identical to QinQ.
- **#435**: Upstream PR [#584](https://github.com/irontec/sngrep/pull/584) adds configurable themes. It remains a proposal, not an accepted fix.
- **#501**: Upstream PR [#583](https://github.com/irontec/sngrep/pull/583) proposes HEP3/TCP listener handling; test concurrent clients, partial/coalesced frames, TLS-independent behavior, and UDP compatibility before closure.
- **#503**: Upstream PR [#582](https://github.com/irontec/sngrep/pull/582) proposes Codec Column; SDP offer-vs-answer, early media, re-INVITE and rejected m-lines require regression coverage.

## Concrete merge criteria

1. Reproduce against current upstream master before declaring any historical issue fixed.
2. Add a regression fixture for parser/capture issues whenever possible.
3. Run both Autotools `make check` and CMake build (plus sanitizers for memory safety).
4. PR descriptions must state exactly which issue is **fully** fixed and which related issues are only partially addressed.
5. Tag/close requests require maintainers' permission; avoid misleading ownership or mass status changes.
