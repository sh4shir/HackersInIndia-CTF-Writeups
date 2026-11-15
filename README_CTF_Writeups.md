# HackersInIndia CTF — Writeups

This repository records 25 HackersInIndia CTF challenges, their objectives, analysis notes and accepted flags.

> **Accuracy note:** Challenge descriptions and flags are transcribed from the supplied 55-page CTF PDF. The original downloadable handouts are not available. Accordingly, artifact-dependent solution notes below are investigation workflows inferred from the challenge statements, not claims of independently tested commands or payloads. The **Two Layers** decoding sequence is reproducible from the visible challenge text.

## Challenge index

| Challenge | Area | Accepted flag |
|---|---|---|
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

## Detailed notes

### Not to Soon

**Challenge:** The prompt describes a recently created social account, repeated captions and a countdown-like sequence. It instructs the solver to inspect the account @not_so_soon_ and read every post, including content that may not be obvious at first glance.

**Analysis / workflow:** Review the account chronologically rather than relying on the profile summary. Inspect captions, image text, replies, linked content and any ordering clues. Compare repeated phrases and countdown changes; assemble the scattered pieces only after recording their order.

**Reproducibility:** The supplied prompt identifies the account and the need to inspect all posts. The exact post contents and the specific extraction sequence are not present in the PDF.

**Accepted flag:** `InIt{n0t_s0_s00n_but_f0und_1t}`

### Red John’s Footprints

**Challenge:** The challenge provides the username rEdJOHn203 and the clue “I never stop pushing my work out there.” It asks the solver to search online and follow the trail.

**Analysis / workflow:** Search the exact username across relevant public platforms. Correlate accounts using matching handles, profile details and cross-links. Inspect public posts, repositories and other published material for a consistent clue trail; validate the final phrase against the required flag format.

**Reproducibility:** The prompt supports username-based OSINT and cross-platform correlation. The PDF does not preserve the external pages visited or the precise clue chain.

**Accepted flag:** `InIt{th3_truth_w4s_1n_th3_w4t3r}`

### Where Am I?

**Challenge:** The task asks for the city, country and daylight-saving time abbreviation associated with a photograph. The flag format is CITY_COUNTRY_TIMEZONE.

**Analysis / workflow:** Inspect the supplied image for landmarks, signs, architecture and environmental clues. Use reverse-image search or map imagery to narrow the location, then verify the city and country. Finally check the local daylight-saving rule for the relevant date and use the requested standard abbreviation.

**Reproducibility:** The PDF shows the accepted location/time-zone flag, but not the original photograph itself, so the visual identification cannot be independently replayed from this PDF alone.

**Accepted flag:** `InIt{PERUGIA_ITALY_CEST}`

### Red John Returns

**Challenge:** The challenge links to a GitHub repository associated with the username rEdJOHn203 and asks the solver to follow the account’s latest work. It explicitly says the complete flag can be checked by hashing it.

**Analysis / workflow:** Open the linked repository and inspect its files, commit history, branches and relevant paths. Follow the challenge-specific clues in the repository rather than guessing from the username. Once the candidate flag is assembled, compute its SHA-256 digest and compare it with the verification value supplied by the challenge materials, if available.

**Reproducibility:** The repository URL and SHA-256 verification instruction are visible in the prompt. The exact repository contents and expected digest are not reproduced in the PDF.

**Accepted flag:** `InIt{smiley_1988_teacup_3389_lisbon}`

### The Ink That Bled

**Challenge:** The prompt is a layered narrative referencing the Dollmaker, Reid, Hoffman, twelve eyes, an untagged post and an alias hidden beneath broken threads.

**Analysis / workflow:** Treat the text as a set of OSINT and puzzle clues. Identify the named fictional references and the likely platform or account implied by “untagged” and “broken threads.” Search for the alias, then inspect the referenced post and read surrounding text, comments or thread structure for the hidden message.

**Reproducibility:** The prompt supplies thematic clues, but the actual external post/thread is not included in the PDF. The exact discovery path therefore cannot be reproduced.

**Accepted flag:** `InIt{u_5h0uLd_h3ar_Taba_ch4k3}`

### Two Layers

**Challenge:** A captured string is described as double-encoded. The visible ciphertext is `VmFWZ3tlMGdfZ3U zYV9vNjRfMWZfYT BnX2YzcGhlM WdsfQ==` (spaces are line-wrap artifacts). The required flag prefix is InIt.

**Analysis / workflow:** First Base64-decode the supplied string. The resulting text is `VaVg{e0g_gu3a_o64_1f_a0g_f3phe1gl}`. Apply ROT13 to the decoded text to obtain the flag. The clue says the administrator double-encoded the value; the operations are Base64 decoding followed by ROT13.

**Reproducibility:** This is reproducible from the challenge text. The Base64 input shown in the PDF is line-wrapped; remove visual spaces before decoding.

**Accepted flag:** `InIt{r0t_th3n_b64_is_n0t_s3curity}`

### Le Chiffre

**Challenge:** The prompt gives a ciphertext-like string and the note: “The key is the hour when everything goes quiet.”

**Analysis / workflow:** Interpret the note as a key-discovery hint. Test the intended time-related key against the provided ciphertext using the cipher family suggested by the challenge title and ciphertext structure. Validate the plaintext against the InIt{...} format and the accepted flag.

**Reproducibility:** The ciphertext is visible, but the PDF does not include the external forum context or enough information to prove the exact key derivation. The accepted flag itself indicates that a Vigenère guess was not the answer; do not document a specific cipher/key as fact without the missing context.

**Accepted flag:** `InIt{v1g3n3r3_w4s_n0t_th3_4nsw3r}`

### Known Plaintext PRNG

**Challenge:** The prompt describes a custom stream-like cipher that XORs four-byte blocks with a 32-bit key. The key evolves using a predictable linear congruential generator, and the flag format reveals the first plaintext block.

**Analysis / workflow:** Use the known flag prefix as a known-plaintext block. XOR that plaintext block with the first ciphertext block to recover the initial 32-bit keystream value. Use the LCG relationship described in the challenge to generate subsequent key states, then XOR each ciphertext block and reconstruct the plaintext.

**Reproducibility:** This is the method implied by the challenge description. The `encrypt.zip` attachment containing ciphertext and generator parameters is missing, so numerical state recovery and code output cannot be reproduced.

**Accepted flag:** `InIt{kn0wn_pl41nt3xt_4tt4cks_4r3_c00l}`

### The Careless Twins

**Challenge:** Two servers use RSA public keys generated by a custom prime generator. The challenge provides both public keys and a ciphertext and hints that the prime generator is weak.

**Analysis / workflow:** Compare the RSA moduli for shared factors. Compute the greatest common divisor of the two moduli; a non-trivial GCD reveals a prime reused across keys. Factor the affected modulus, derive the private key, and decrypt the ciphertext. If the GCD is 1, investigate the supplied prime-generation weakness rather than assuming shared-prime reuse.

**Reproducibility:** The RSA weakness and artifacts are described, but the `careless.zip` attachment is absent. The actual moduli, ciphertext and decryption transcript cannot be verified.

**Accepted flag:** `InIt{n3v3r_r3us3_pr1m3s_1n_rs4}`

### The Fractured Key

**Challenge:** The challenge provides intercepted ciphertext and a script used to generate keys. It warns that the true flag is hidden among fake decryptions and that the key-generation script is suspect.

**Analysis / workflow:** Read the key-generation script to identify its random source, seed, state size and output transformations. Reproduce the generator, enumerate the realistically small candidate key space, decrypt the ciphertexts, and distinguish the genuine plaintext by the exact InIt{...} structure and surrounding consistency checks.

**Reproducibility:** The prompt supports weak/predictable randomness and candidate filtering. The script and ciphertext attachment are missing, so no exact generator reconstruction is possible here.

**Accepted flag:** `InIt{p3ud0_r4nd0m_1s_n0t_r4nd0m_k3y_sp4c3_t00_sm4ll}`

### Deleted Evidence

**Challenge:** The prompt describes a disk image captured after an intruder deleted source code and product-design files. It emphasizes that deletion does not necessarily erase file contents.

**Analysis / workflow:** Work from a forensic copy of the image. Identify the filesystem and partition layout, inspect directory entries and unallocated space, and recover deleted file contents where their blocks remain. Search recovered data for project/source artifacts and correlate timestamps and filesystem metadata.

**Reproducibility:** The `evidence.img` disk image is missing. The flag is available, but file-system offsets, recovered filenames and exact recovery commands are not.

**Accepted flag:** `InIt{d3l3t3d_but_n0t_g0n3}`

### Locked Notes

**Challenge:** The prompt describes an Android app-data directory from a Secure Notes application. The app appears locked, but its data folder was acquired.

**Analysis / workflow:** Inventory the extracted application files and database formats. Inspect SQLite databases, preferences, backups and app-specific encryption metadata. Determine whether the note is stored in plaintext, protected by a recoverable key, or encoded in an application-specific format; recover the note from the acquired data.

**Reproducibility:** The `securenote` archive is missing, so the database schema, encryption implementation and actual recovery steps cannot be established from the prompt alone.

**Accepted flag:** `InIt{s3cur3_n0t3s_n0t_s0_s3cur3}`

### EC2-Dropper

**Challenge:** The challenge describes an unauthorized scheduled script at `/opt/agent/vault.py`. The vault key is derived at runtime from the EC2 instance identity and is not stored on disk.

**Analysis / workflow:** Inspect the script to identify the key-derivation inputs and vault encryption routine. Review the supplied host logs for the instance identity values and relevant execution context. Reconstruct the same key derivation, decrypt the vault, and extract the operator’s configuration note. Treat instance metadata and host identity as evidence sources, not as a generic secret.

**Reproducibility:** The incident archive containing the script, vault and logs is missing. The exact derivation and decryption code cannot be asserted without those files.

**Accepted flag:** `InIt{imds_k3y3d_s3cr3t_v4ult}`

### Keychain-Crumbs

**Challenge:** The prompt describes an information stealer exfiltrating browser credentials, Keychain data and system information over plaintext HTTP. It asks for the stolen profile and a secret accidentally leaked in cleartext.

**Analysis / workflow:** Extract the packet capture from the supplied archive and inspect HTTP conversations. Reassemble relevant requests and responses, identify the destination host and transferred profile data, and search plaintext bodies, headers and parameters for the leaked secret. Use stream-following and protocol filtering to preserve the context of each transfer.

**Reproducibility:** The `capture.zip` packet capture is missing. The flag is visible, but the actual host profile and leaked value cannot be reproduced.

**Accepted flag:** `InIt{k3ych4in_crumbs_l34k3d_0v3r_pl41n_http}`

### Leaky History

**Challenge:** The prompt says a secrets file was committed and later removed from the visible Git history. A recovered repository archive is provided in the original challenge.

**Analysis / workflow:** Inspect all Git refs and objects, not only the current branch log. Search dangling commits and unreachable blobs, inspect their trees, and recover the deleted secrets file from the historical object that still references it. A normal working-tree search is insufficient when the commit was removed from the visible branch history.

**Reproducibility:** The `repo.tar.gz` archive is missing. The Git-object recovery workflow is clear from the prompt, but the specific object ID and recovered content cannot be reproduced.

**Accepted flag:** `InIt{d4ngl1ng_c0mm1t_l34k}`

### Beepy

**Challenge:** The challenge supplies an audio file and explicitly says to wrap the answer in InIt{A11_CAP5}.

**Analysis / workflow:** Inspect the audio and determine whether the beeps encode Morse. Use a waveform or spectrogram to distinguish short and long tones and the gaps between letters and words. Translate the sequence, normalize the result to uppercase as requested, and wrap it in the flag format.

**Reproducibility:** The `audio.wav` file is missing, so the tone sequence and transcription cannot be replayed.

**Accepted flag:** `InIt{B33PY_M0RS3_1S_C00L}`

### Weird Sound

**Challenge:** The prompt asks whether the solver has heard of a spectrum analyzer and says to wrap the answer in InIt{}.

**Analysis / workflow:** Load the supplied WAV into a spectrum or spectrogram viewer. Inspect frequency components and time intervals for structured signals or encoded text. Decode the visible pattern and preserve the exact capitalization and punctuation required by the flag.

**Reproducibility:** The audio file is missing. The prompt supports spectrum/spectrogram analysis, but the signal itself is not available for independent decoding.

**Accepted flag:** `InIt{W0ah_y0u_S33_M3!}`

### Hidden Giveaway

**Challenge:** The challenge provides a tourist map of India and says something is hidden in plain sight.

**Analysis / workflow:** Inspect the image at full resolution. Check color channels, contrast, unusual blue regions, pixel-level patterns and image metadata. If the clue points to a color-specific message, isolate or enhance the relevant channel and read the hidden content.

**Reproducibility:** The image attachment is missing. The flag is recorded, but the exact hiding technique and extraction operation cannot be confirmed from the screenshot.

**Accepted flag:** `InIt{h1ding_1n_blue_ligh7}`

### Camera Lost & Found

**Challenge:** The challenge provides a collection of camera photographs and gives the archive password `camera-found`. It asks for hidden information in one of the pictures.

**Analysis / workflow:** Extract the archive using the provided password. Inspect image metadata (EXIF), thumbnails, comments and embedded previews. Compare files for unusual metadata or appended data, and inspect suspicious images with appropriate forensic tools.

**Reproducibility:** The image archive is missing. The prompt explicitly provides the password, but the exact image and metadata field containing the answer are not present.

**Accepted flag:** `InIt{h1ding_1n_m3tad4t4}`

### The Last Announcement

**Challenge:** The challenge describes a tampered Indian Railways announcement recording and asks the solver to investigate what was hidden.

**Analysis / workflow:** Inspect the recording with audio-forensics tools. Review waveform and spectrogram views, listen at different speeds, examine channel differences and check for appended or embedded data. Compare suspicious sections with the surrounding announcement to locate the concealed content.

**Reproducibility:** The `Train_Announcement` audio attachment is missing, so the exact manipulation and extraction method cannot be independently confirmed.

**Accepted flag:** `InIt{h1ding_f1l3s_1n_4ud10}`

### The Troll’s Ticket

**Challenge:** The prompt describes a tampered Indian Railways tour ticket passing through Delhi, Mumbai, Chennai and Kolkata. It says the supplied files may not be what they appear to be.

**Analysis / workflow:** Identify each file by its actual signature rather than its extension. Inspect archives and embedded files, validate file types, and follow the sequence of artifacts associated with the four cities. Reconstruct the intended journey/order and recover the ticket content.

**Reproducibility:** The challenge archive is missing. The prompt supports file-type and multi-artifact investigation, but not a precise list of commands or the exact file sequence.

**Accepted flag:** `InIt{journey_4cr0ss_1ndia}`

### Second

**Challenge:** The prompt describes an easy web challenge involving invoices and sorting reports, with a local web service and a handout archive.

**Analysis / workflow:** Inspect the application’s input handling and the handout source code. Trace how invoice/report values are stored and later used. The accepted flag identifies second-order injection as the relevant class: investigate whether data stored in one request is later interpreted as executable query or command syntax in a separate operation.

**Reproducibility:** The handout and service are not available here. The flag identifies the vulnerability class, but the exact injection point and payload cannot be responsibly reconstructed.

**Accepted flag:** `InIt{s3c0nd_0rd3r_1nj3ct10n}`

### Cash Now

**Challenge:** The prompt describes a loan platform with archived and encrypted documents and provides a web service plus a local handout. The accepted flag identifies SSRF and a tool/endpoint clue.

**Analysis / workflow:** Review the application routes and document-fetching workflow. Identify any server-side URL retrieval feature, then determine whether user-controlled URLs can reach internal or unintended destinations. Use only the isolated CTF environment and the provided handout to enumerate reachable resources and inspect the image-processing path indicated by the challenge.

**Reproducibility:** The application source/handout is missing. The flag text points to SSRF and a PNG-crushing enumeration clue, but exact endpoints and payloads are unknown.

**Accepted flag:** `InIt{ssrf_pNgcrush_3numt00l0ng}`

### Super Pickle

**Challenge:** The prompt describes a web application called Super Pickle and asks why people warn against Pickle.

**Analysis / workflow:** Inspect the application’s use of Python serialization and identify whether untrusted serialized data is accepted. In an authorized local challenge, trace the serialization/deserialization flow and determine whether unsafe pickle handling or a parsing/filter bypass is involved. The accepted flag specifically points to a Unicode pickle bypass.

**Reproducibility:** The live service and source/handout are not available here. Do not treat generic pickle exploitation as the confirmed exact path; the flag indicates a Unicode-related bypass.

**Accepted flag:** `InIt{Un1c0d3_P1ckl3_Byp4ss}`

### Super Blind

**Challenge:** The prompt says a catalog search appears harmless, a filter watches input, and some record fields are private. It asks whether those fields can be leaked.

**Analysis / workflow:** Inspect the catalog search request and response behavior. Determine whether the backend constructs SQL from user-controlled input and whether the filter can be bypassed. In the isolated challenge, use boolean/time-based inference to test blind SQL injection and extract only the intended challenge data.

**Reproducibility:** The service and handout are missing. The flag identifies blind SQL injection, but exact syntax, filter bypass and extraction payloads cannot be verified.

**Accepted flag:** `InIt{blind_sql_1nj3ct10n_g0brrrr!@#}`

## Reproducible example: Two Layers

The challenge describes a two-stage encoding. The accepted flag and clue indicate that the
encoded value is Base64 applied to a ROT13-transformed flag. Reverse the operations when decoding:
Base64 first, then ROT13. The low-resolution screenshot does not provide a safe basis for
retyping every ciphertext character, so the input string is intentionally not reproduced here.

Save the exact challenge-provided Base64 value to `encoded.txt`, then run:

```bash
base64 -d encoded.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

Accepted plaintext:

```text
InIt{r0t_th3n_b64_is_n0t_s3curity}
```

## Final notes

The accepted flags are transcribed from the correct-submission entries in the supplied PDF.
For fully reproducible walkthroughs of artifact-dependent challenges, the original handout
archives are needed. Add exact commands, scripts, intermediate outputs and screenshots only
after rerunning those artifacts.
