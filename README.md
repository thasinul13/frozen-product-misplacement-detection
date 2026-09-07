# Frozen Product Misplacement & Cold-Chain Breach Detection

**MRes Research Project — CQUniversity Sydney**

## Overview

This project develops a computer vision framework for detecting misplaced 
frozen and refrigerated products in supermarket environments, and for 
identifying potential cold-chain breaches that result from prolonged 
exposure outside frozen storage. The framework combines a YOLOv8-based 
object detection model with a PSO (Particle Swarm Optimisation)-optimised 
decision layer to classify and flag misplaced items in real time.

## Motivation

Frozen products left in non-frozen aisles are a common but under-addressed 
issue in retail environments — they pose food safety risks, cause 
unnecessary waste, and represent a cold-chain compliance gap that is 
difficult to monitor manually at scale. This project is directly motivated 
by real-world observations made while working as a nightfill team member 
in a supermarket, where frozen items were frequently found abandoned in 
non-frozen aisles.

## Approach

- **Detection model:** YOLOv8 object detection, fine-tuned to identify 
  frozen/refrigerated products across supermarket aisle imagery.
- **Decision layer:** A PSO-optimised layer tunes key detection parameters 
  (confidence floor, overlap threshold, edge margin, minimum object size, 
  frozen-class confidence, minimum detection count) to reduce false 
  positives/negatives in misplacement classification.
- **Synthetic data generation:** A Stable Diffusion inpainting pipeline 
  (with ControlNet conditioning) generates photorealistic synthetic 
  training images — placing frozen items into real supermarket background 
  images with physics-informed visual effects (condensation, frost melt, 
  surface darkening) derived from physical models (Magnus formula, 
  Newton's Law of Cooling, Beer-Lambert Law, Fresnel reflection).
- **Real-world data:** A real-image dataset is being collected in-store, 
  following a structured field protocol (aisle categories, placement 
  codes, paired empty/misplaced photos, distance and angle guidelines).
- **Evaluation:** A three-way ablation study compares (a) synthetic data 
  only, (b) real data only, and (c) synthetic pre-training with real-data 
  fine-tuning.

## Repository Structure
