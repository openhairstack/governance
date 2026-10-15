# Glossary — the words we use, in plain English

We wrote this for journalists, newcomers, and family members who asked what we actually do.
If a doc here confuses you, that's a bug — tell us.

## The hair stuff

**Follicle (hair follicle).** The tiny structure in your scalp that grows a hair. Think of it
as a hair factory.

**Follicular unit (FU).** The bundle of hairs that share one factory opening. Naturally grows
in 1–6 hairs per unit, usually. Counting how many hairs a unit contains is *the* useful number
in hair transplant work, because the whole bundle gets moved together.

**Graft.** Unit of transplant currency = one follicular unit, removed and re-implanted. A
"2,000-graft" surgery moves 2,000 of these bundles.

**FUE (Follicular Unit Extraction).** The modern transplant method: punch out individual
grafts from the back of the head and place them where needed. Robots like ARTAS do this.

**Donor area / recipient area.** The back and sides of your head (where hair keeps growing —
the "donor") and the thinning regions at the front and top (the "recipient").

**Miniaturization.** When follicles shrink under the influence of hormones (mostly DHT) and
start producing thinner, shorter, less visible hairs. This is what "pattern baldness" actually is.

**Norwood scale.** The standard chart (1–7) of how far male pattern baldness has progressed.
Our demo's readout of it is explicitly a rough heuristic — read the disclaimer.

**DHT.** Dihydrotestosterone. The hormone that shrinks susceptible follicles in male pattern
baldness.

**Androgenetic alopecia (AGA).** The clinical name for male/female pattern hair loss.

## The machine-learning stuff

**Model / model weights.** Software that has learned from examples ("weights" are the
trained files — what we publish).

**Epoch.** One full pass through the training data. 60 epochs = the model has seen every
image 60 times.

**mAP / mAP50.** Mean Average Precision — our accuracy score. mAP50 counts a detection as
correct if the box overlaps by >50%; mAP50-95 is stricter. Higher = better.

**Box (bounding box) / OBB (oriented bounding box).** The rectangle the model draws around
each follicle. An OBB is a rotated rectangle — better for angled follicles, harder to label.

**Class.** The label category. Our classes are fu1…fu5 — the hair-count buckets.

**Baseline.** The first, deliberately simple, fully-published model. A baseline isn't the
best model — it's the floor everyone improves on.

**Overfit / split leakage.** Overfit: memorizing training images instead of learning.
Leakage: the same image appearing in both training and test sets, which inflates scores.
Our validator checks for both.

**Dataset split.** Splitting data into train/val/test sets. testing on what you trained on
is how papers fool themselves (and reviewers).

## The licenses

**Apache 2.0** (our code) — do anything you want, keep the copyright notice, credit us.
Patent grant included.

**CC BY 4.0** (our data/docs) — reuse freely, credit us.

**AGPL-3.0** (some libraries we depend on, and one candidate dataset) — strong share-alike
license; anything you build on AGPL code must also be open-source under AGPL. This is why
we keep an explicit licensing doc.

**Provenance.** Documented origin of every dataset: where it came from, under what license,
with which attribution. If we can't prove provenance, we don't ship it.

## The project words

**Wet lab.** Lab with chemicals and tissue. We have none; our data is cameras and
annotations, so this problem is reachable for software people.

**Benchmark.** A shared, fixed test set so different teams' numbers mean the same thing. We're
building one for follicle detection.

**Kill criteria.** Written conditions under which we stop the project. Most projects don't
have them. Most projects that don't, also never stop. Ours are in the whitepaper.

**Charter.** Our one-page rules document: what we do, what we never do, how we decide. Read
it before anything else.
