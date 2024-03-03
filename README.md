#[derive(PartialEq, Debug)]
enum Status {
    LegendaryTriumph,
    QualifiedSuccess,
    FortuitousRevival,
    IndeterminateStalemate,
    RecoverableSetback,
    DireMisadventure,
    AbjectFailure,
}

impl Status {
    pub fn from_i32(value: i32) -> Option<Self> {
        match value {
            0 => Some(Status::LegendaryTriumph),
            1 => Some(Status::QualifiedSuccess),
            2 => Some(Status::FortuitousRevival),
            3 => Some(Status::IndeterminateStalemate),
            4 => Some(Status::RecoverableSetback),
            5 => Some(Status::DireMisadventure),
            6 => Some(Status::AbjectFailure),
            _ => None,
        }
    }
}

fn main() {
    let s = Status::from_i32(1);
    assert_eq!(s, Some(Status::QualifiedSuccess));

    let s = Status::from_i32(9);
    assert_eq!(s, None);
}
