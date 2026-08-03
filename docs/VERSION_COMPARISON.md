# Version Comparison

## Baseline Information

Repository: <https://github.com/YHH-jimmy/LIO-SAM_rtioms.git>

Baseline branch: `main`

Baseline commit: `cb07b90538d8bb70ac56a04dc72ffab46acd88bb`

Baseline commit date: `2026-03-31T19:45:59+08:00`

Baseline commit subject: `initial commit for LIO-SAM-ros2`

Voxel branch: `voxel-map-ros2`

Branch start merge-base: `cb07b90538d8bb70ac56a04dc72ffab46acd88bb`

Document creation date: `2026-08-03T00:00:00+08:00`

## Architecture Comparison

| Version | Deskew | Frontend Representation | Registration | Backend | Current Role |
| --- | --- | --- | --- | --- | --- |
| `main` | LIO-SAM | Corner and surface features | Feature scan-to-map | iSAM2 | Baseline |
| Standalone VoxelMap reference | External deskew cloud | Adaptive voxel and planes | Voxel point-to-plane optimizer | None | Validation reference |
| `voxel-map-ros2` | Target: LIO-SAM deskew | Target: adaptive voxel and planes | Target: integrated voxel scan-to-map | Target: LIO-SAM backend | Development branch |

## Experimental Comparison Template

| Metric | main baseline | voxel-map-ros2 | Difference | Status |
| --- | --- | --- | --- | --- |
| Source input frames | | | | |
| Callback frames | | | | |
| Callback completeness | | | | |
| Input points | | | | |
| Downsampled points | | | | |
| Root voxel hits | | | | |
| Planar leaf hits | | | | |
| Accepted correspondences | | | | |
| Registration success frames | | | | |
| Map update frames | | | | |
| Mean frontend runtime | | | | |
| Optimizer runtime | | | | |
| APE translation RMSE | | | | |
| RPE translation RMSE | | | | |
| Rotational APE RMSE | | | | |
| Rotational RPE RMSE | | | | |
| CPU utilization | | | | |
| Peak memory | | | | |
| Output trajectory duration | | | | |

## Comparison Rules

- Use the same dataset segment, bag start/end timestamps and input frame identity.
- Record playback rate, callback completeness and every parameter difference.
- Do not compare trajectories when callback inputs differ materially without documenting the difference.
- Do not report rotational metrics when ground truth is invalid or position-only.
- Do not treat topic publication as registration success; use frame diagnostics for pose validity and map updates.

## Change Log

- Created `voxel-map-ros2` from `cb07b90538d8bb70ac56a04dc72ffab46acd88bb`.
- Added branch purpose and version-comparison methodology.
- Added current standalone VoxelMap validation evidence.
- No Adaptive Voxel Map source integration is included in this documentation commit.
