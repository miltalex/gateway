Renamed the generated xDS compressor filters for `BackendTrafficPolicy`
configurations that set `minContentLength` or custom Gzip/Brotli/Zstd settings.
The filter name now carries a digest of those settings (for example
`envoy.filters.http.compressor.gzip` becomes
`envoy.filters.http.compressor.gzip/<digest>`). Configurations that only select a
compressor type keep the previous filter name. Update any `EnvoyPatchPolicy` or
tooling that matches the old filter names.
