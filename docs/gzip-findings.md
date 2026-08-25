# Gzip Decompression Research Findings

## Objective

Attempt to determine the compression format of `.vlt` files to enable extraction of the `skin.xml` and assets.

## Test Methodology

The following test was performed on `references/skins-windows/default.vlt`:

1. Read the file into a byte array.
2. Attempted decompression using `System.IO.Compression.GZipStream`.
3. Observed the resulting output and errors.

## Results

- **Observation:** The `GZipStream` decompression failed.
- **Evidence:** The raw byte dump of the file does not start with the standard Gzip magic numbers (`1f 8b`).
- **Conclusion:** `.vlt` files are not compressed using the standard Gzip format.

## Updated Hypothesis

Since neither ZIP nor Gzip formats were successful, the `.vlt` format is likely:

1. A proprietary binary format used by VLC.
2. A different archive format (e.g., Zlib without Gzip headers, or a custom wrapper).

## Next Steps

- Analyze the `references/skins2-create.html` documentation for mentions of the packaging process.
- Look for open-source tools or scripts capable of unpacking VLC `.vlt` files.
- Focus on utilizing `winamp2.xml` as a structural proxy until a reliable extraction method is found.
