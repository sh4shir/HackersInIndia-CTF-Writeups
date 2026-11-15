# HackersInIndia CTF Writeups

Writeups for 25 challenges from the **HackersInIndia CTF**, covering OSINT, cryptography, forensics, steganography and web security. Flags use the format `InIt{...}`.

Author: Your Name

## Files

| File | Description |
| --- | --- |
| `HackersInIndia_CTF_Writeups.pdf` | The full writeup, one challenge per page (30 pages) |
| `README.md` | This file |

## Writeup format

Every challenge in the PDF follows the same template:

1. **Overview**: the challenge description and the objective
2. **Reconnaissance & Triage**: what was given and how it was first inspected
3. **Analysis & Vulnerability Discovery**: the core mechanism and the flaw, explained simply
4. **Exploitation & Extraction**: setup, execution and the flag
5. **Rabbit Holes (Optional)**: dead ends worth knowing about
6. **Key Takeaways**: the core lesson and the techniques used

## Challenges

| Challenge | Category | Accepted flag |
| --- | --- | --- |
| Not to Soon | OSINT / social-media investigation | `InIt{n0t_s0_s00n_but_f0und_1t}` |
| Red John’s Footprints | OSINT | `InIt{th3_truth_w4s_1n_th3_w4t3r}` |
| Where Am I? | Image geolocation / OSINT | `InIt{PERUGIA_ITALY_CEST}` |
| Red John Returns | OSINT / GitHub investigation | `InIt{smiley_1988_teacup_3389_lisbon}` |
| The Ink That Bled | OSINT / clue correlation | `InIt{u_5h0uLd_h3ar_Taba_ch4k3}` |
| Two Layers | Cryptography | `InIt{r0t_th3n_b64_is_n0t_s3curity}` |
| Le Chiffre | Cryptography | `InIt{v1g3n3r3_w4s_n0t_th3_4nsw3r}` |
| Known Plaintext PRNG | Cryptography | `InIt{kn0wn_pl41nt3xt_4tt4cks_4r3_c00l}` |
| The Careless Twins | Cryptography / RSA | `InIt{n3v3r_r3us3_pr1m3s_1n_rs4}` |
| The Fractured Key | Cryptography / weak randomness | `InIt{p3ud0_r4nd0m_1s_n0t_r4nd0m_k3y_sp4c3_t00_sm4ll}` |
| Deleted Evidence | Digital forensics | `InIt{d3l3t3d_but_n0t_g0n3}` |
| Locked Notes | Mobile / application forensics | `InIt{s3cur3_n0t3s_n0t_s0_s3cur3}` |
| EC2-Dropper | Cloud / host forensics | `InIt{imds_k3y3d_s3cr3t_v4ult}` |
| Keychain-Crumbs | Network forensics | `InIt{k3ych4in_crumbs_l34k3d_0v3r_pl41n_http}` |
| Leaky History | Git forensics | `InIt{d4ngl1ng_c0mm1t_l34k}` |
| Beepy | Audio / Morse | `InIt{B33PY_M0RS3_1S_C00L}` |
| Weird Sound | Audio / spectrum analysis | `InIt{W0ah_y0u_S33_M3!}` |
| Hidden Giveaway | Steganography | `InIt{h1ding_1n_blue_ligh7}` |
| Camera Lost & Found | Image forensics / metadata | `InIt{h1ding_1n_m3tad4t4}` |
| The Last Announcement | Audio forensics | `InIt{h1ding_f1l3s_1n_4ud10}` |
| The Troll’s Ticket | File forensics | `InIt{journey_4cr0ss_1ndia}` |
| Second | Web security / injection | `InIt{s3c0nd_0rd3r_1nj3ct10n}` |
| Cash Now | Web security / SSRF | `InIt{ssrf_pNgcrush_3numt00l0ng}` |
| Super Pickle | Web security / Unicode handling | `InIt{Un1c0d3_P1ckl3_Byp4ss}` |
| Super Blind | Web security / blind SQL injection | `InIt{blind_sql_1nj3ct10n_g0brrrr!@#}` |

## Accuracy notes

- The original challenge handouts (archives, images, audio, disk images and source code) are not available. Only **Two Layers** can be decoded from the visible challenge text alone.
- For the other challenges, the steps describe a defensible investigation plan. They are not commands that were run, and no commands, payloads, file contents or intermediate outputs have been invented.
- The two code sketches (the SHA-256 check in *Red John Returns* and the shared-prime RSA solver in *The Careless Twins*) are labelled as illustrative.
- **Two Layers:** the Base64 string as transcribed from a low-resolution screenshot decodes to `InIt{r0t_th3n_b64_1s_n0t_s3cur1ty}`, which differs from the accepted flag in two characters. Verify it against the original challenge.
- Flags were transcribed from the correct-submission entries visible in the event screenshots.

## Improving these writeups

If you have the original handouts, rerun each challenge and add the exact commands, scripts, intermediate outputs and screenshots. Add any real dead ends to the **Rabbit Holes** section, since those are what beginners learn the most from.
