<img src="assets/logo.png" width="112" height="112" alt="SortRuns logo">

# SortRuns

Summarize equal-value runs in a nondecreasing integer stream. This Blyx library is part of the collections and storage collection.

A duplicate row should not look like a newly added key. Compare distinct sets and report repeated occurrences separately. [Python, grouping consecutive keys](https://docs.python.org/3/library/itertools.html#itertools.groupby)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-sortruns.git
cd blyx-sortruns
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-sortruns) · [Package page](https://www.blyx-lang.space/packages/sortruns) · [Handbook](https://doc.blyx-lang.space/guide/chaffinch)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-sortruns.git vendor/sortruns
```

```blyx
use vendor::sortruns::sortruns;

fn main() {
    let values = [1, 1, 2, 3, 3, 3];
    let result = sortruns_profile(values);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
3
3
3
```

## API

`sortruns_profile(values)`

Returns [distinct values, longest run length, first key with that run]. Empty input returns [0,0,0]. Rejects descending keys. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| values | Vector of values, each a exact signed integer |

## In use

[Chaffinch](https://github.com/Rahulchaube1/blyx-chaffinch) uses this module to reconcile sorted collection snapshots without materializing their union.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-sortruns/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The package artwork uses [Lucide icons](https://lucide.dev/license); see [artwork notices](assets/NOTICE.txt).

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
